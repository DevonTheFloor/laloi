<template>
  <div>
    <v-card class="ma-7">
      <h1>{{ page.title }}</h1>
      <p>{{ page.description }}</p>
      <figure class="illustration">
        <img :src="page.img">
      </figure>
      <nuxt-content :document="page" />
    </v-card>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params, error }) {
    const page = await $content('articles', params.slug)
      .fetch()
      .catch((err) => {
        // eslint-disable-next-line no-console
        console.error(err)
        error({ statusCode: 404, message: 'Page not found' })
      })

    return {
      page
    }
  },
  head () {
    return {
      title: this.page.title,
      meta: [
        { hid: 'description', name: 'description', content: this.page.description },
        // Open Graph
        { hid: 'og:title', property: 'og:title', content: this.page.title },
        { hid: 'og:description', property: 'og:description', content: this.page.description },
        { property: 'og:type', content: 'Web site' },
        { property: 'og:image', content: this.page.img },
        // Twitter Card
        { hid: 'twitter:title', name: 'twitter:title', content: this.page.title },
        { hid: 'twitter:description', name: 'twitter:description', content: this.page.description },
        // Twitter Summary card images must be at least 200x200px
        { name: 'twitter:image', content: this.page.img }
      ]
    }
  }
}
</script>

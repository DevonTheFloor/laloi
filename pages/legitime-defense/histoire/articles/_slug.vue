<template>
  <div>
    <v-card class="ma-7 pa-7">
      <h1 class="ma-3 text-center">
        {{ page.title }}
      </h1>
      <p class="ma-4">
        {{ page.description }}
      </p>
      <figure class="illustration">
        <img :src="page.img" class="ma-auto imgart">
      </figure>
      <nuxt-content :document="page" />
    </v-card>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params, error }) {
    const page = await $content('defense/histoire', params.slug)
      .fetch()
      .catch((err) => {
        // eslint-disable-next-line no-console
        console.error(err)
        error({ statusCode: 404, message: 'Nous ne trouvons pas cette page' })
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

<style>
h2 {
  margin-left: 4%;
}
p {
  font-size: 1rem;
  text-align: justify;
}
.vdo {
  width: 90%;
  margin: 0%;
  display: flex;
  justify-content: center;
}
.imgart {
  display: block;
  max-width: 70%;
  min-width: 50%;
}
@media screen and (max-with: 550px){
  p{
    margin: 0px;
  }
}
</style>

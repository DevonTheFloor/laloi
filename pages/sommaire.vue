<template>
  <v-row class="d-flex flex-column align-center">
    <v-col class="d-flex flex-column align-center ma-5">
      <img
        src="/favicon.ico"
        alt="nul n'est censé ingonrer la loi logo"
        class="mb-5"
      >
      <h1>Sommaire blog</h1>
      <!--<blockquote class="blockquote">
        &#8220;First, solve the problem. Then, write the code.&#8221;
        <footer>
          <small>
            <em>&mdash;John Johnson</em>
          </small>
        </footer>
      </blockquote>-->
    </v-col>
    <v-divider />
    <v-card>
      <ul>
        <li v-for="article in sommaire" :key="article.id">
          <div class="print pa-5">
            <v-card-title>{{ article.title }}</v-card-title>
            <v-card-text> {{ article.description }} </v-card-text>
            <v-btn
              :to="`./blog/${article.slug}`"
            >
              Lire
            </v-btn>
          </div>
        </li>
      </ul>
      <nuxt-content :document="sommaire" />
    </v-card>
  </v-row>
</template>

<script>
export default {
  async asyncData ({ $content, error }) {
    const sommaire = await $content('articles').only(['title', 'description', 'slug'])
      .fetch()
      .catch((err) => {
        // eslint-disable-next-line no-console
        console.error(err)
        error({ statusCode: 404, message: 'Page not found' })
      })
    return {
      sommaire
    }
  }
}
</script>

<style>
v-card {
  border: 2px solid red;
}

</style>

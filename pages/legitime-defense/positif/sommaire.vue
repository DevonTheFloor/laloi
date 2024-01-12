<template>
  <v-row class="d-flex flex-column align-center">
    <v-col class="d-flex flex-column align-center ma-5">
      <img
        src="/favicon.ico"
        alt="nul n'est censé ingonrer la loi logo"
        class="mb-5"
      >
      <h1>Etat du droit positif en légitime défense</h1>
      <v-card-text>
        Par les textes de loi, la réglementation mais aussi par la jurisprudence de la Cour de Cassation; ici nous ferons le tour de toutes le régles inhérente à la légitime défense.
      </v-card-text>
    </v-col>
    <v-divider />
    <ul>
      <li v-for="article in sommaire" :key="article.id">
        <v-card>
          <div class="print pa-5">
            <v-card-title>{{ article.title }}</v-card-title>
            <v-card-text> {{ article.write }} </v-card-text>

            <v-card-text> {{ article.description }} </v-card-text>
            <v-btn
              :to="`/legitime-defense/positif/articles/${article.slug}`"
            >
              Lire
            </v-btn>
          </div>
        </v-card>
        <v-divider class="pa-3" />
      </li>
    </ul>
    <nuxt-content :document="sommaire" />
  </v-row>
</template>

<script>
export default {
  async asyncData ({ $content, error }) {
    const sommaire = await $content('defense/positif').only(['title', 'description', 'write', 'slug'])
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
ul {
  list-style-type: none;
  padding-left: 0px;
}
</style>

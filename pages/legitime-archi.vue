<template>
  <v-row class="d-flex flex-column align-center">
    <v-col class="d-flex flex-column align-center ma-5">
      <img
        src="/favicon.ico"
        alt="nul n'est censé ingonrer la loi logo"
        class="mb-5"
      >
      <h1>Dossier Légitime Défense</h1>
      <v-card-text>
        Le dossier légitime defense va s'organiser autour de trois axes tous aussi important les uns que les autres. L'histoire pour comprendre comment ça à commencé. L'évolution jurisprudencielle pour comprendre comment ça a évolué et l'état du droit positif pour savoir ou est ce que nous en sommes aujourd'hui.<ol>
          <li>Le droit positif</li>
          <li>L'evolution jurisprudentielle</li>
          <li>L'histoire</li>
        </ol>
      </v-card-text>
    </v-col>
    <v-divider />
    <h2>Etat du droit positif</h2>
    <v-card-text>Ce que dit le droit acctuellement</v-card-text>
    <ul class="list-article">
      <li v-for="article in positif" :key="article.id">
        <v-card>
          <div class="print pa-5">
            <v-card-title>{{ article.title }}</v-card-title>
            <v-card-text> {{ article.write }} </v-card-text>

            <v-card-text> {{ article.description }} </v-card-text>
            <v-btn
              :to="`/legitime-defense/positif/${article.slug}`"
            >
              Lire
            </v-btn>
          </div>
        </v-card>
        <v-divider class="pa-3" />
      </li>
    </ul>
    <nuxt-content :document="positif" />
    <v-divider />
    <h2>Evolution jurisprudencielle</h2>
    <v-card-text>A partir des textes originaux; comment en sommes nous arrivé à la situation acctuelle.</v-card-text>
    <ul class="list-article">
      <li v-for="article in evolution" :key="article.id">
        <v-card>
          <div class="print pa-5">
            <v-card-title>{{ article.title }}</v-card-title>
            <v-card-text> {{ article.write }} </v-card-text>

            <v-card-text> {{ article.description }} </v-card-text>
            <v-btn
              :to="`/legitime-defense/evolution/${article.slug}`"
            >
              Lire
            </v-btn>
          </div>
        </v-card>
        <v-divider class="pa-3" />
      </li>
    </ul>
    <nuxt-content :document="evolution" />
    <v-divider />
    <h2>Histoire</h2>
    <v-card-text>En commençant depuis le commencement comme on dit en français!</v-card-text>
    <ul class="list-article">
      <li v-for="article in histoire" :key="article.id">
        <v-card>
          <div class="print pa-5">
            <v-card-title>{{ article.title }}</v-card-title>
            <v-card-text> {{ article.write }} </v-card-text>

            <v-card-text> {{ article.description }} </v-card-text>
            <v-btn
              :to="`/legitime-defense/histoire/${article.slug}`"
            >
              Lire
            </v-btn>
          </div>
        </v-card>
        <v-divider class="pa-3" />
      </li>
    </ul>
    <nuxt-content :document="histoire" />
  </v-row>
</template>

<script>
export default {
  async asyncData ({ $content, error }) {
    const histoire = await $content('dossier-lg/histoire').only(['title', 'description', 'write', 'slug'])
      .fetch()
      .catch((err) => {
        // eslint-disable-next-line no-console
        console.error(err)
        error({ statusCode: 404, message: 'Page not found' })
      })
    const evolution = await $content('dossier-lg/evolution').only(['title', 'description', 'write', 'slug'])
      .fetch()
      .catch((err) => {
        // eslint-disable-next-line no-console
        console.error(err)
        error({ statusCode: 404, message: 'Page not found' })
      })
    const positif = await $content('dossier-lg/positif').only(['title', 'description', 'write', 'slug'])
      .fetch()
      .catch((err) => {
        // eslint-disable-next-line no-console
        console.error(err)
        error({ statusCode: 404, message: 'Page not found' })
      })
    return {
      histoire,
      evolution,
      positif
    }
  }
}

</script>
<style>
  v-card {
    border: 2px solid red;
  }
  .list-article {
    list-style-type: none;
    padding-left: 0px;
  }
  </style>

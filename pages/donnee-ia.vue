<template>
  <div>
    <v-toolbar
      color="grey"
      dense
      dark
    >
      <v-toolbar-title class="ma-auto">
        Systèmes de traitement de données assistés par une IA
      </v-toolbar-title>

      <v-spacer />

      <v-menu
        left
        bottom
      >
        <template #activator="{ on, attrs }">
          <v-btn
            icon
            v-bind="attrs"
            v-on="on"
          >
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item
            v-for="(lettre, i) in alphabet"
            :key="i"
            @click="() => {}"
          >
            <v-list-item-title>{{ lettre }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-toolbar>
    <v-divider
      class="pa-4"
    />
    <v-card>
      <v-img
        class="ma-auto"
        max-width="55%"
        height="200px"
        src="https://intelligence-artificielle.com/wp-content/uploads/2022/02/IA-base-de-donnees-prise-en-charge-3.jpg"
      />
      <v-card-text
        class="text-center pa-8"
      >
        Alors, ici on va traiter des bases de données à caractère personnel qui sont assistées par une Intelligence Artificielle. Parce que, l'Etat, des bases de données , il en a watts millions, et, en verité, on en n'a pas grand chose à faire, vu que ça n'est que le numérisation des dossiers qu'on a déjà tous dans les administrations diverses et variées. Là ou ça devient original, c'est quand il y a une Itelligence Artificielle qui à accés à ces données et s'en sert pour prendre des décisions. Dans ce cas de figure, il me semble totalement impératif d'en informer le citoyen.
      </v-card-text>
    </v-card>
    <v-col
      v-for="({ nom, presentation, date, linkJO, linkBlog, linkVid}, i) in sibd"
      :key="i"
      class="col-lg-12 pa-8"
    >
      <h2 class="text-center">
        {{ nom }}
      </h2>
      <v-card class="ma-4 pa-4">
        <p> {{ presentation }} </p>
        <v-btn
          :href="linkJO"
          target="_blank"
        >
          JORF du {{ date }}
        </v-btn>
        <v-btn
          :to="linkBlog"
          target="_blank"
        >
          Article Blog
        </v-btn>
        <v-btn
          :href="linkVid"
        >
          Video
        </v-btn>
      </v-card>
    </v-col>
  </div>
</template>

<script>
export default {
  data () {
    return {
      urlImg: 'https://www.docteurclic.com/galerie-photos/image_3229_400.jpg',
      alphabet: [
        'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'
      ],
      sibd: [
        {
          nom: 'Champollion',
          presentation: "Le traitement « Champollion » a pour finalité de structurer et de mettre à disposition des administrations relevant du champ du travail, de l'emploi et de l'insertion, des données pour l'accomplissement de leurs missions.[...]2° Favoriser le recours à l'intelligence artificielle et son développement, notamment en élaborant des outils, des référentiels et des méthodologies constituant des modèles prédictifs dans la mise en œuvre des politiques publiques ;",
          date: '16/10/22',
          linkJO: 'https://www.legifrance.gouv.fr/jorf/id/JORFTEXT000046431088',
          linkBlog: './blog/champollion',
          linkVid: ''
        }
      ]
    }
  },
  head () {
    return {
      title: 'Traitement de données/IA',
      meta: [
        { hid: 'description', name: 'description', content: 'Déremboursement de médicaments et équiements médicaux qui paraissent au JO. Il me semlble important de les rapporter içi, car m\'est avis, que les personnnes touchées pas ses mesures ne sont pas au courants. Le fait est que cela touche, très souvent, des medicaments et autres équipement visant à traiter des maladies lourdes. Je transmets l\'info , esperant que vous ne serez pas pris au dépourvu.' },
        // Open Graph
        { hid: 'og:title', property: 'og:title', content: 'Déremboursement médicaments' },
        { hid: 'og:description', property: 'og:description', content: 'Déremboursement de médicaments et équiements médicaux qui paraissent au JO. Il me semlble important de les rapporter içi, car m\'est avis, que les personnnes touchées pas ses mesures ne sont pas au courants. Le fait est que cela touche, très souvent, des medicaments et autres équipement visant à traiter des maladies lourdes. Je transmets l\'info , esperant que vous ne serez pas pris au dépourvu.' },
        { property: 'og:type', content: 'Web site' },
        { property: 'og:image', content: 'https://www.docteurclic.com/galerie-photos/image_3229_400.jpg' },
        // Twitter Card
        { hid: 'twitter:title', name: 'twitter:title', content: 'Déremboursement médicaments' },
        { hid: 'twitter:description', name: 'twitter:description', content: 'Déremboursement de médicaments et équiements médicaux qui paraissent au JO. Il me semlble important de les rapporter içi, car m\'est avis, que les personnnes touchées pas ses mesures ne sont pas au courants. Le fait est que cela touche, très souvent, des medicaments et autres équipement visant à traiter des maladies lourdes. Je transmets l\'info , esperant que vous ne serez pas pris au dépourvu.' },
        // Twitter Summary card images must be at least 200x200px
        { name: 'twitter:image', content: 'https://www.docteurclic.com/galerie-photos/image_3229_400.jpg' }
      ]
    }
  }
}

</script>

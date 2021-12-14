<template>
  <div>
    <v-toolbar
      color="grey"
      dense
      dark
    >
      <v-toolbar-title class="ma-auto">
        Dérembopursement de médicaments et équipements medicaux
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-menu
        left
        bottom
      >
        <template v-slot:activator="{ on, attrs }">
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
    <v-card>
      <v-card-text
        class="text-center"
      >
        Déremboursement de médicaments et équiements médicaux qui paraissent au JO. Il me semlble important de les rapporter içi, car m'est avis, que les personnnes touchées pas ses mesures ne sont pas au courants. Le fait est que cela touche, très souvent, des medicaments et autres équipement visant à traiter des maladies lourdes. Je transmets l'info , esperant que vous ne serez pas pris au dépourvu.
      </v-card-text>
    </v-card>
    <v-col
      v-for="({ nom, presentation, cause, date, link}, i) in deremb"
      :key="i"
      class="col-lg-12 pa-4"
    >
      <h2 class="text-center">
        {{ nom }}
      </h2>
      <v-card class="ma-4 pa-4">
        <p> Produit: {{ presentation }} </p>
        <p> Cause: {{ cause }} </p>
        <v-btn
          :href="link"
          target="_blank"
        >
          JORF du : {{ date }}
        </v-btn>
      </v-card>
    </v-col>
  </div>
</template>

<script>
export default {
  data () {
    return {
      alphabet: [
        'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'
      ],
      deremb: [
        {
          nom: 'Humida',
          presentation: '40, 80 mg (adalimumab), solution injectable',
          cause: 'Medicament d\'execption',
          date: '14/12/21',
          link: 'https://www.legifrance.gouv.fr/jorf/id/JORFTEXT000044483108'
        }
      ]
    }
  }
}

</script>

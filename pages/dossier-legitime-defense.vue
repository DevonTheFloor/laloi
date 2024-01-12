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
          <li>L'evolution jurisprudencielle</li>
          <li>L'histoire</li>
        </ol>
      </v-card-text>
    </v-col>
    <v-divider class="space" />
    <h2 class="row">
      Etat du droit positif
    </h2>

    <v-card-text>Ce que dit le droit acctuellement au travers des textes legislatif et réglementaires. Mais aussi et peut être, surtout, au travers de l'interprétation qu'en fait la</v-card-text>
    <v-btn
      variant="tonal"
      to="/legitime-defense/positif/sommaire"
    >
      Page Droit Positif
    </v-btn>
    <v-divider class="space ma-10" />
    <h2>Evolution jurisprudencielle</h2>
    <v-card-text>A partir des textes originaux; comment en sommes nous arrivé à la situation acctuelle.</v-card-text>
    <v-btn
      variant="tonal"
      to="legitime-defense/evolution/sommaire"
    >
      Page Evolution Jurisprudencielle
    </v-btn>
    <v-divider class="space ma-10" />
    <h2>Histoire</h2>
    <v-card-text>En commençant depuis le commencement comme on dit en français! Depuis le premier code penal de 1791 jusqu'a aujourd'hui.</v-card-text>
    <v-btn
      variant="tonal"
      to="legitime-defense/histoire/sommaire"
    >
      Page Histoire
    </v-btn>
    <v-divider class="space ma-10" />
  </v-row>
</template>

<script>

</script>

<style>
v-card {
  border: 2px solid red;
}
.list-article {
  list-style-type: none;
  padding-left: 0px;
}
h2 {
  padding: 3px;
}
</style>

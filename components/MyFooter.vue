<template>
  <v-footer
    color="#292929"
    height="100"
    class="d-flex flex-column justify-center align-center pa-4"
  >
    <!-- Liens sociaux centrés horizontalement -->
    <div class="mb-3">
      <ol class="d-flex justify-center list-none pa-0 ma-0" style="gap: 1.5rem;">
        <li>
          <a href="https://x.com/NulnciLaloi" class="ref">Twitter</a>
        </li>
        <li>
          <a href="https://www.youtube.com/@nulnestcenseignorerlaloi3025" class="ref">YouTube</a>
        </li>
        <li>
          <a href="https://www.linkedin.com/in/nul-laloi-905809286/" class="ref">LinkedIn</a>
        </li>
      </ol>
    </div>

    <!-- Copyright centré -->
    <div class="title font-weight-light grey--text text--lighten-1 text-center">
      &copy; 2021 - {{ new Date().getFullYear() }} — Made with 💜 by <a href="https://devonthefloor.github.io" target="_blank" class="ref">Thierry</a>
    </div>
  </v-footer>
</template>

<style scoped>
/* Supprime les puces de la liste */
.list-none {
  list-style: none;
}

/* Style des liens */
.ref {
  color: #bb86fc; /* ou la couleur que tu veux */
  text-decoration: none;
  font-weight: 500;
  transition: color 0.2s;
}

.ref:hover {
  color: #ffffff;
  text-decoration: underline;
}
</style>

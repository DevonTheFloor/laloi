<template>
  <div>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
        <v-btn
          class="unik"
          href="http://nulnestcenseignorerlaloi.fr/blog"
        >
          <v-icon left>mdi-chart-bubble</v-icon>
          MON BLOG
        </v-btn>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.stop="fixed = !fixed"
      >
        <v-icon>mdi-minus</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar>
  </div>
</template>
<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Bienvenue',
          to: '/'
        },
        {
          icon: 'mdi-apps',
          title: 'Légitime Défense',
          to: '/dossier-legitime-defense'
        },
        {
          icon: 'mdi-database-search-outline',
          title: 'IA/Données personnels',
          to: '/donnee-ia'
        },
        {
          icon: 'mdi-atom',
          title: 'Centrale Nucléaire',
          to: '/modif-nucléaire'
        },
        {
          icon: 'mdi-alert-octagram',
          title: 'Action Citoyenne',
          to: '/action-citoyenne'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Menu escamotable'
    }
  }
}
</script>
<style scoped>
.unik {
  color:red;
  border: 1px solid red;
  background-color: rgb(239, 233, 233);
  width:100%;
}
.unik:hover {
  color: white;
  font-size: larger;
  border:1px solid white;
  background-color: rgb(121, 121, 247);
}
</style>

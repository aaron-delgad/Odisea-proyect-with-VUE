<template>
  <div class="page-container">
    <md-app>
      <md-app-toolbar style="background-color:#ff3333" class="row">
        <md-button
          class="md-icon-button col-1 col-sm-1 col-md-1 col-lg-1 col-xl-1"
          @click="toggleMenu"
        >
          <md-icon style="color:white">menu</md-icon>
        </md-button>
        <span class="md-title col-1 col-sm-2 col-md-2 col-lg-3 col-xl-3 fw--500"
          style="color:white">Agente de Prensa</span
        >
        <div
          class="md-toolbar-section-end col-1 col-sm-1 offset-md-3 col-md-4 offset-lg-4 col-lg-3 offset-xl-4 col-xl-3"
        >
          <span style="color:white">{{ emailUser }}</span>
          <md-avatar>
            <img :src="require(`@/assets/img/${photoUser}`)" v-bind:alt="photoUser" />
          </md-avatar>
        </div>
      </md-app-toolbar>

      <md-app-drawer :md-active.sync="menuVisible" md-persistent="full">
        <md-toolbar class="md-transparent" md-elevation="0">
          <img
            src="@/assets/img/Making Connexion_Logo - color-08.png"
            alt="making"
          />
        </md-toolbar>
        <md-divider></md-divider>
        <md-list>
          <md-list-item class="listMenu"
            ><md-icon>dashboard</md-icon
            ><span class="md-list-item-text">Dashboard</span></md-list-item
          >
          <md-list-item class="listMenu"
            ><md-icon>person</md-icon
            ><span class="md-list-item-text">Clientes</span></md-list-item
          >
          <md-list-item class="listMenu"
            ><md-icon>report</md-icon
            ><span class="md-list-item-text">Reportes</span></md-list-item
          >
          <md-list-item class="listMenu"
            ><md-icon>trending_up</md-icon
            ><span class="md-list-item-text">Metas</span></md-list-item
          >
          <md-list-item class="listMenu"
            ><md-icon>add</md-icon
            ><span class="md-list-item-text">Plugins</span></md-list-item
          >
        </md-list>
      </md-app-drawer>

      <md-app-content>
        <router-view />
      </md-app-content>
    </md-app>
  </div>
</template>

<script>
export default {
  name: "HomeView",
  components: {},

  data: () => ({
    emailUser: "Aaron Delgado",
    photoUser: "foto-Raul-Aaron.jpg",
    menuVisible: true,
  }),
  methods: {
    goMetas() {
      this.$router.push("metas");
    },
    toggleMenu() {
      this.menuVisible = !this.menuVisible;
    },
  },
};
</script>

<style lang="scss" scoped>
.md-app {
  min-height: 100vh;
  border: 1px solid rgba(#000, 0.12);
}

.md-drawer {
  width: 230px;
  max-width: calc(100vw - 125px);
}
.listMenu {
  cursor: pointer;
  :hover {
    background-color: #f4f5f8;
  }
}
</style>

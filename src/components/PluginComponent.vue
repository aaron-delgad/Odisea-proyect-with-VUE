<template>
  <div>
    <div class="row">
      <div
        v-for="item in dataPlugin"
        :key="item.id"
        class="col-12 col-sm-12 col-md-12 col-lg-6 col-xl-6 px-4"
      >
        <md-card style="background-color: #f4f5f8">
          <md-card-header>
            <md-card-header-text>
              <div class="md-title c--secondary-making">{{ item.title }}</div>
              <md-card-content>
                <div>{{ item.detail }}</div>
              </md-card-content>
              <md-card-content>
                <div>{{ item.costo }}</div>
              </md-card-content>
            </md-card-header-text>

            <md-card-media md-big>
              <img
                :src="require(`@/assets/img/${item.image}`)"
                :alt="item.image"
              />
            </md-card-media>
          </md-card-header>

          <md-card-actions>
            <md-button class="md-accent" @click="activarPlugin()" v-if="estadoPlugin">Instalar Ahora</md-button>
            <md-button class="md-accent" @click="desactivarPlugin()" v-if="!estadoPlugin">Desactivar</md-button>
          </md-card-actions>
        </md-card>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PluginComponent",
  components: {},

  data: function () {
    return {
      estadoPlugin: true,
      dataPlugin: [
        {
          title: "Metas",
          detail:
            "Le permitira tener mejor control en las metas de sus trabajadores",
          costo: "Costo adicional: S/. 35.00",
          image: "metas.webp",
          alt: "logo",
        },
        {
          title: "Reportes",
          detail: "Le permitira Tener Mayor control en sus reportes",
          costo: "Costo adicional: S/. 25.00",
          image: "reporte.jpg",
          alt: "logo",
        },
      ],
    };
  },
  methods: {
    activarPlugin() {
      this.estadoPlugin = false;
    },
    desactivarPlugin() {

    }
  }
};
</script>

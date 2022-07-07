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
                <div><span class="fw--700">Costo adicional:</span> S/.{{ item.costo }}</div>
                <div><span class="fw--700">Ultima actualización:</span> hace {{ item.updateLast }} meses</div>
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
            <div v-if="spinnerInst">
            <md-progress-spinner class="md-accent" :md-diameter="30" md-mode="indeterminate" ></md-progress-spinner>
            <p>Instalando ...</p>
            </div>
            <div v-if="spinnerDes">
            <md-progress-spinner class="md-accent" :md-diameter="30" md-mode="indeterminate" ></md-progress-spinner>
            <p>Desinstalando ...</p>
            </div>
            <md-button class="md-accent" @click="statePlugin(item.state)" v-if="item.state">Instalar Ahora</md-button>
            <md-button class="md-accent" @click="statePlugin(!item.state)" v-if="!item.state">Desactivar</md-button>
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
      spinnerInst: false,
      spinnerDes: false,
      dataPlugin: [
        {
          id: "1",
          title: "Metas",
          detail:
            "Le permitira tener mejor control en las metas de sus trabajadores",
          costo: "35.00",
          updateLast: "2",
          image: "metas.webp",
          state: true,
          alt: "logo",
        },
        {
          id: "2",
          title: "Reportes",
          detail: "Le permitira Tener Mayor control en sus reportes",
          costo: "25.00",
          updateLast: "1",
          image: "reporte.jpg",
          state: false,
          alt: "logo",
        },
      ],
    };
  },
  methods: {
    statePlugin(state) {
      console.log(state);
      if(state) {
          this.spinnerInst = true;
      }else{
        this.spinnerDes = true;
      }
      
      
      
    },
  }
};
</script>

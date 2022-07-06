<template>
  <div>
    <h4 class="c--primary">
      Puedes activar las funcionalidades que deses, solo debes dar clic en el
      botón <span class="fw--700 fz--xxl">Instalar ahora</span>.
    </h4>
    <md-divider></md-divider>
    <div class="mt-5">
      <PluginComponent />
    </div>
  </div>
</template>

<script>
import PluginComponent from "./../components/PluginComponent.vue";
export default {
  name: "PluginView",
  components: { PluginComponent },
};
</script>

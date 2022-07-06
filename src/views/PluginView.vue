<template>
  <div>
    Plugin
    <div>
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

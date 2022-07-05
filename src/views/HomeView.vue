<template>
  <div>
    <h1>Home</h1>
    <b-button variant="outline-primary" v-on:click="goMetas()">Ir a Metas</b-button>
  </div>
</template>

<script>
export default {
  name: "HomeView",
  components: {},
  
  methods: {
    goMetas() {
      this.$router.push("metas");
    }
  }
}
</script>
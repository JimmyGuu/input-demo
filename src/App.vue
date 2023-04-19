<template>
  <div id="app">
    <AwesomeInput v-model="address" @update:value="onChange" />
  </div>
</template>

<script>
import AwesomeInput from "@/components/AwesomeInput.vue";

export default {
  name: 'App',
  components: {
    AwesomeInput,
  },
  data() {
    return {
      address: "",
    }
  },
  methods: {
    onChange(newValue) {
      newValue = newValue || "";
      this.$nextTick(() => {
        this.address = newValue.replace(/[^a-zA-Z]/g, "").toUpperCase();
      });
    },
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

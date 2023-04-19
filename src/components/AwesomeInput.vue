<template>
  <div class="awesome-input">
    <textarea v-model="valueInner" cols="30" rows="10"></textarea>
  </div>
</template>

<script>
export default {
  name: "AwesomeInput",
  model: {
    prop: "value",
    event: "update:value",
  },
  props: {
    value: String,
  },
  data() {
    return {};
  },
  computed: {
    valueInner: {
      get() {
        return this.value;
      },
      set(newValue) {
        this.$emit("update:value", newValue);
      },
    },
  },
  methods: {
  },
}
</script>

<style lang="css" scoped></style>

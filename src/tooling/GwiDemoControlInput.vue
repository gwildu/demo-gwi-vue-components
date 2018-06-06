<template>
  <span>
    <label :for="id">{{label}}</label>
    <input :id="id" :type="type" v-model="value" @change="change" />
  </span>
</template>

<script>
export default {
  name: 'GwiDemoControlInput',
  props: {
    value: {},
    type: {
      type: String,
      default() {
        return "text";
      }
    },
    label: {
      type: String,
      default() {
        return "Control label";
      }
    }
  },
  computed: {
    id() {
      return this.label.replace(/ /, "");
    }
  },
  methods: {
    change() {
      this.$emit("change", this.value);
    }
  }
};
</script>

<style lang="sass" scoped>

</style>

<template>
  <component :is="`GwiDemoControl${capitalizeFirst(type)}`" :type="type" controlData="data"/>
</template>

<script>
import GwiDemoControlString from "./GwiDemoControlString";
import GwiDemoControlBoolean from "./GwiDemoControlBoolean";
import GwiDemoControlNumber from "./GwiDemoControlNumber";
import GwiDemoControlEnum from "./GwiDemoControlEnum";

const supportedTypes = ["string", "boolean", "number", "enum"];
export default {
  name: "GwiDemoControl",
  components: {
    GwiDemoControlString,
    GwiDemoControlBoolean,
    GwiDemoControlNumber,
    GwiDemoControlEnum
  },
  props: {
    type: {
      type: String,
      default() {
        return "string";
      },
      required: true,
      validator(type) {
        return supportedTypes.indexOf(type) > -1;
      }
    },
    controlData: {
      type: Object,
      default() {
        return {};
      },
      required: false
    }
  },
  methods: {
    change(data) {
      this.$emit("change", data);
    },
    capitalizeFirst(string) {
      return string.charAt(0).toUpperCase() + string.slice(1)
    }
  }
};
</script>

<style lang="scss">

</style>

<template>
  <div class="demoCase">
    <GwiHeading markup-level="2" styling-level="3">{{name}}</GwiHeading>
    <div class="controls">controls</div>
    <div class="wrapper">
      <slot></slot>
    </div>
  </div>
</template>

<script>
import GwiHeading from "gwi-vue-components";

export default {
  name: "GwiDemoCase",
  components: {
    GwiHeading
  },
  props: {
    name: {
      type: String,
      default() {
        return "Component name";
      },
      required: true
    },
    controls: {
      type: Array,
      default() {
        return [];
      },
      required: false
    }
  },
  methods: {
    change(data) {
      this.$emit({ name: this.name, ...data });
    }
  }
};
</script>

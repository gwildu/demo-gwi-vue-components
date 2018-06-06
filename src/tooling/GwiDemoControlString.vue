<template>
  <GwiDemoControlInput type="text" v-model="controlData.defaultValue" @change="change" :label="controlData.label"/>
</template>

<script>
import GwiDemoControlInput from './GwiDemoControlInput'

export default {
  name: 'GwiDemoControlString',
  components: {
    GwiDemoControlInput
  },
  props: {
    controlData: {
      type: Object,
      required: true,
      default() {
        return {
          defaultValue: '',
          label: 'Control name'
        }
      },
      validator(controlData) {
        return controlData.defaultValue && controlData.label && typeof controlData.defaultValue === 'string' && typeof controlData.label === 'string'
      }
    },
  },
  methods: {
    change() {this.$emit("change", this.value);}
  }
}
</script>

<style lang="sass" scoped>

</style>


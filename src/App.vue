<template>
  <div id="app">
    <GwiGlobals>
        <GwiCardDemo />
        <GwiHeadingDemo />
    </GwiGlobals>
  </div>
</template>

<script>
import GwiGlobals from "gwi-vue-components/GwiGlobals";
import GwiCardDemo from './components/GwiCardDemo'
import GwiHeadingDemo from './components/GwiHeadingDemo'

export default {
  name: "App",
  components: {
    GwiGlobals,
    GwiCardDemo,
    GwiHeadingDemo
  }
};
</script>

<style lang="scss">
#app {
  position: relative;
  width: 100%;
  margin: 0;
  padding: 0;
}
</style>

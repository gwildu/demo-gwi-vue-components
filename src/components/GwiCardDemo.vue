<template>
  <div class="component">
    <GwiDemoCase name="Without props">
      <GwiCard>default</GwiCard>
    </GwiDemoCase>
    <div class="group">
        <GwiHeading :styling-level="3">Without props</GwiHeading>
        <div class="wrapper">
          <GwiCard>default</GwiCard>
        </div>
      </div>
      <div class="group">
        <GwiHeading :styling-level="3" :margin-top="true">Elevation level</GwiHeading>
        <div class="controls">
          <label>level: </label>
          <input v-model="elevationLevel" type="number"/>
        </div>
        <div class="wrapper">
          <GwiCard :level="elevationLevel">elevation level</GwiCard>
        </div>
      </div>
      <div class="group">
        <GwiHeading :styling-level="3" :margin-top="true">Spacings</GwiHeading>
        <div class="controls">
          <label>padding: </label>
          <input v-model="padding" type="checkbox" />
          <label> margin-top: </label>
          <input v-model="marginTop" type="checkbox" />
          <label> margin-bottom: </label>
          <input v-model="marginBottom" type="checkbox" />
        </div>
        <div class="wrapper">
          <GwiCard 
            :padding="padding"
            :margin-top="marginTop"
            :margin-bottom="marginBottom"
            layout="fill"
            level="3">
            <img class="image" src="https://res.cloudinary.com/gwildu/image/upload/s--L0cn6Pjw--/v1528171787/common/duck1.jpg">
          </GwiCard>
        </div>
      </div>
      <div class="group">
        <GwiHeading :styling-level="3" :margin-top="true">Layout</GwiHeading>
        <div class="controls">
          <label>layout: </label>
          <select v-model="layout">
            <option>fill</option>
            <option>stretch</option>
          </select>
        </div>
        <div class="wrapper">
          <GwiCard :layout="layout" :padding="false" level="3">
            <img class="image" src="https://res.cloudinary.com/gwildu/image/upload/s--A0n5WYxO--/c_scale,h_333,w_500/v1528171785/common/duck2.jpg" />
          </GwiCard>
        </div>
    </div>
  </div>
</template>

<script>
import GwiCard from "gwi-vue-components/GwiCard";
import GwiHeading from "gwi-vue-components/GwiHeading";
import GwiDemoCase from "../tooling/GwiDemoCase"

export default {
  name: "GwiCardDemo",
  components: {
    GwiCard,
    GwiHeading,
    GwiDemoCase
  },
  data() {
    return {
      elevationLevel: 3,
      padding: false,
      marginTop: false,
      marginBottom: false,
      layout: "fill"
    };
  }
};
</script>

<style lang="scss">
.wrapper {
  margin: 20px;
  border: 2px dotted rgba(255, 100, 0, 0.25);
  pading: 0;
}
.group {
  padding-bottom: 20px;
  border-bottom: 1px dashed rgba(0, 0, 0, 0.3);
}
.image {
  width: 100%;
  display: block;
}
.controls {
  margin: 20px;
}
</style>

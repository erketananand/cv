<template>
  <li>
    <div>
      <strong>{{ skill.name }}</strong>
      <div class="stars">
        <div
          class="percent"
          :style="{width: skill.rating}"
        ></div>
      </div>
    </div>
  </li>
</template>

<script lang='ts'>
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';
@Component
export default class MySkill extends Vue {
  @Prop({ type: Object, required: true }) skill!: any;
}
</script>

<style scoped>
.stars {
  margin-right: 1000px;
  position: relative;
  float: right;
  font-size: 20pt;
  height: 1em;
  line-height: 1em;
}

.stars:before {
  content: '\2606\2606\2606\2606\2606';
  float: right;
  z-index: 1;
}

.stars .percent {
  position: absolute;
  left: 0;
  float: right;
  overflow: hidden;
  z-index: -1;
}

.stars .percent:after {
  content: '\2605\2605\2605\2605\2605';
  color: rgb(150, 150, 150);
}
</style>

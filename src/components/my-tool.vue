<template>
  <li>
    <div>
      <strong>{{ tool.name }}:</strong>
      <span>{{tool.value}}</span>
    </div>
    </div>
  </li>
</template>

<script lang='ts'>
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';
@Component
export default class MyTool extends Vue {
  @Prop({ type: Object, required: true }) tool!: any;
}
</script>

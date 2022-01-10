<template>
  <li>
    <h6>{{ edu.degree }} ({{ edu.yearOfPassing }} - {{edu.grade}})</h6>
    <span>{{ edu.school }}, {{ edu.location }}</span>
  </li>
</template>

<script lang='ts'>
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';
@Component
export default class MyEducation extends Vue {
  @Prop({ type: Object, required: true }) edu!: any;
}
</script>

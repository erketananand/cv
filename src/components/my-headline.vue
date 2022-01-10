<template>
  <div class="row">
    <h1 class="col-8 text-left">
      <strong>{{ name }}</strong>
    </h1>
    <div class="col-4 text-right">
      <div>{{ contact.email }}</div>
      <div>{{ contact.phone }}</div>
    </div>
  </div>
</template>

<script lang='ts'>
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';
@Component
export default class MyHeadline extends Vue {
  @Prop({ type: Object, required: true }) contact!: any;
  @Prop({ type: String, required: true }) name!: string;
}
</script>

<style scoped>
.text-right {
  text-align: right;
}
</style>

<template>
  <li>
    <strong>{{ medium.name }}:</strong> <a
      :href="medium.url"
      target="_blank"
    >{{ medium.url }}</a>
  </li>
</template>

<script lang='ts'>
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';
@Component
export default class MySocialMedia extends Vue {
  @Prop({ type: Object, required: true }) medium!: any;
}
</script>

<template>
  <li>
    <h6>
      {{ experience.title }}, {{ experience.company }}, {{ experience.location }}
    </h6>

    <div>{{ experience.date }}</div>

    <div class="details">
      <div v-if="experience.desc.info">
        <div>{{ experience.desc.info }}</div>
      </div>

      <div v-if="experience.desc.resp">
        <ul>
          <li v-for="resp in experience.desc.resp">{{ resp }}</li>
        </ul>
      </div>

      <div v-if="experience.desc.tools">
        <div>
          <strong>Tools:</strong> {{ experience.desc.tools }}
        </div>
      </div>

      <div v-if="experience.desc.services">
        <div>
          <strong>3rd-party Services:</strong> {{ experience.desc.services }}
        </div>
      </div>
    </div>
  </li>
</template>

<script lang='ts'>
import Vue from 'vue';
import { Component, Prop } from 'vue-property-decorator';
@Component
export default class MyExperience extends Vue {
  @Prop({ type: Object, required: true }) experience!: any;
}
</script>

<style scoped>
h6 {
  background: #ebebeb;
  border-radius: 4px;
  padding: 3px 8px;
}
ul {
  padding: 0 0 0 18px;
}
.date {
  padding: 0 0 0 15px;
}
.details {
  margin: 0 0 0 15px;
}
</style>

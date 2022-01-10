<template>
  <div id="app">
    <Cv></Cv>
  </div>
</template>

<script lang='ts'>
import Vue from 'vue';
import { Component } from 'vue-property-decorator';
import Cv from './components/cv.vue';

@Component({
  components: {
    Cv
  }
})
export default class App extends Vue {

}
</script>

<style scoped>
body {
  font-family: 'Optima-Regular', 'Optima', 'Avenir', Helvetica, Arial,
    sans-serif;
}

h6 {
  font-weight: bolder;
}
</style>

<!-- <style src="./scss/app.scss" lang="scss" scoped></style> -->
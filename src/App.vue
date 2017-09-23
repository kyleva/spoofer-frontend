<template>
  <div id="app">
    <h3>spoofer</h3>
    <SpooferForm></SpooferForm>
    <SpooferList v-bind:values="data.spoofItems"></SpooferList>
  </div>
</template>

<script>
import 'whatwg-fetch'

import SpooferForm from './components/SpooferForm'

export default {
  name: 'app',
  data() {
    return {
      spoofItems: [],
    }
  },
  components: {
    SpooferForm,
  },
  methods: {
    createSpoofItem(spoofItem) {
      // bypass fetch
      this.spoofItems.push({
        title: spoofItem.title,
        description: spoofItem.description,
        image: spoofItem.image,
        spoofId: spoofItem.spoofId,
      })
    },
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

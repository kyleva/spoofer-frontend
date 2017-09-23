<template>
  <div id="app">
    <h3>spoofer</h3>
    <SpooferForm></SpooferForm>
    <SpooferList :spooferItems="spooferItems"></SpooferList>
  </div>
</template>

<script>
import 'whatwg-fetch'

import SpooferForm from './components/SpooferForm'
import SpooferList from './components/SpooferList'

export default {
  name: 'app',
  data() {
    return {
      spooferItems: [
        {
          title: 'Hello',
          description: 'Hello World',
          image: 'http://placehold.it/250x250',
        },
      ],
    }
  },
  components: {
    SpooferForm,
    SpooferList,
  },
  methods: {
    createSpoofItem(spoofItem) {
      // Bypass fetch for now
      // Consider utilizing await/async here
      // fetch(url, (data) => {
      //   if (!data.success) {
      //     return;
      //   }
      //   else {
      //     this.spooferItems.push({
      //       title: spoofItem.title,
      //       description: spoofItem.description,
      //       image: spoofItem.image,
      //       spoofId: spoofItem.spoofId,
      //     })
      //   }
      // })
      this.spooferItems.push({
        title: spoofItem.title,
        description: spoofItem.description,
        image: spoofItem.image,
        spoofId: Math.floor(Math.random() * 5000),
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

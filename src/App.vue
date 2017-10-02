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
      spooferItems: [],
    }
  },
  components: {
    SpooferForm,
    SpooferList,
  },
  methods: {
    createSpoofItem(spoofItem) {
      fetch(`${process.env.BACKEND_URL}/api/posts`, {
        method: 'POST',
        body: JSON.stringify({
          title: spoofItem.title,
          desc: spoofItem.description,
          img: spoofItem.image,
        }),
        headers: {
          'Content-Type': 'application/json',
        },
      })
      .then(r => r.json())
      .then((s) => {
        this.spooferItems.push({
          title: s.title,
          description: s.desc,
          image: s.img,
          name: s.name,
        })
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

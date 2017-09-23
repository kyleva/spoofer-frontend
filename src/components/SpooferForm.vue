<template>
  <form class="SpooferForm" v-on:submit.prevent="submit">
    <div class="SpooferForm__field">
      <label class="SpooferForm__label">Title</label>
      <input type="text" class="SpooferForm__input SpooferForm__input--text" v-model="title">
    </div>
    <div class="SpooferForm__field">
      <label class="SpooferForm__label">Description</label>
      <input type="text" class="SpooferForm__input SpooferForm__input--text" v-model="description">
    </div>
    <div class="SpooferForm__field">
      <label class="SpooferForm__label">Image</label>
      <input type="text" class="SpooferForm__input SpooferForm__input--text" v-model="image">
    </div>

    <button type="submit" class="SpooferForm__submit">Pop it!</button>
  </form>
</template>

<script>
export default {
  name: 'SpooferForm',
  data() {
    return {
      title: '',
      description: '',
      image: '',
    }
  },
  methods: {
    submit() {
      const { title, description, image } = this

      this.$parent.createSpoofItem({
        title,
        description,
        image,
      })
    },
  },
}
</script>

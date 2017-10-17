<template>
  <form class="SpooferForm" v-on:submit.prevent="submit">
    <div class="SpooferForm__field">
      <label class="SpooferForm__label">Title <span class="break"></span>
        <input type="text" class="SpooferForm__input SpooferForm__input--text" v-model="title">
      </label>
    </div>
    <div class="SpooferForm__field">
      <label class="SpooferForm__label">Description <span class="break"></span>
        <input type="text" class="SpooferForm__input SpooferForm__input--text" v-model="description">
      </label>
    </div>
    <div class="SpooferForm__field">
      <label class="SpooferForm__label">Image <span class="break"></span>
        <input type="text" class="SpooferForm__input SpooferForm__input--text" v-model="image">
      </label>
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

<style scoped>
.SpooferForm {
  margin-left:auto;
  margin-right:auto;
  max-width:600px;
  text-align:left;
}

.SpooferForm__field + .SpooferForm__field {
  margin-top:40px;
}

.SpooferForm__label {
  font-weight:500;
  font-size:22px;
}

.SpooferForm__input {
  margin-top:2px;
}

.SpooferForm__input--text {
  border:0 none;
  border-bottom:2px solid #333;
  color:#666;
  font-size:18px;
  font-weight:200;
  outline-width:0;
  padding:14px 14px 9px 2px;
  width:100%;
}

.SpooferForm__submit {
  background-color:#fff;
  border:2px solid #333;
  cursor:pointer;
  font-size:16px;
  font-weight:600;
  margin-top:30px;
  -webkit-appearance: none;
  padding:16px;
}

span.break { display:block; }
</style>

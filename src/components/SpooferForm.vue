<template>
  <form class="SpooferForm" v-on:submit.prevent="submit">
    <div class="SpooferForm__field">
      <label class="SpooferForm__label">Title <span class="break"></span>
        <input v-validate="'required'" type="text" class="SpooferForm__input SpooferForm__input--text" name="title" v-model="title">
      </label>
      <div class="SpooferForm__error" v-show="errors.has('title')">{{ errors.first('title') }}</div>
    </div>
    <div class="SpooferForm__field">
      <label class="SpooferForm__label">Description <span class="break"></span>
        <input v-validate="'required'" type="text" class="SpooferForm__input SpooferForm__input--text" name="description" v-model="description">
      </label>
      <div class="SpooferForm__error" v-show="errors.has('description')">{{ errors.first('description') }}</div>
    </div>
    <div class="SpooferForm__field">
      <label class="SpooferForm__label">Image <span class="break"></span>
        <input v-validate="{ required: true, url: true }" type="text" class="SpooferForm__input SpooferForm__input--text" name="image" v-model="image">
      </label>
      <div class="SpooferForm__error" v-show="errors.has('image')">{{ errors.first('image') }}</div>
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
      this.$validator.validateAll()
      .then((result) => {
        if (!result) return

        const { title, description, image } = this

        this.$parent.createSpoofItem({
          title,
          description,
          image,
        })
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

.SpooferForm__field {
  margin:20px 0 0;
  padding-bottom:25px;
  position:relative;
}

.SpooferForm__field:first-child {
  margin-top:0;
}

.SpooferForm__field:last-of-type {
  margin-bottom:0;
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

.SpooferForm__error {
  bottom:0;
  color:#f15353;
  font-size:0.9em;
  font-weight:600;
  margin: 5px 0 0;
  position:absolute;
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

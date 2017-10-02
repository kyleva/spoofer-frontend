<template>
  <li class="SpooferList__item">
    <p>
      <strong>Title:</strong> {{ title }}<br/>
      <strong>Description:</strong> {{ description }}<br/>
      <strong>Image:</strong> <a v-bind:href="image">{{ image }}</a>
      <!-- <strong>Link:</strong> <a href="{{ message | backendify }}">1234</a> -->
    </p>
  </li>
</template>

<script>
export default {
  name: 'SpooferItem',
  props: [
    'title',
    'description',
    'image',
  ],
}
</script>

<style scoped>
li {
  list-style:none;
  text-align:left;
}

li+ li {
  margin-top:15px;
}
</style>

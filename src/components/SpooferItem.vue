<template>
  <li class="SpooferList__item">
    <p>
      <strong>Title:</strong> {{ title }}<br>
      <strong>Description:</strong> {{ description }}<br>
      <strong>Image: {{ image }}</strong>
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

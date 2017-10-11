<template>
  <li class="SpooferList__item">
    <div class="SpooferList__item-image">
      <div class="SpooferList__item-image-wrapper">
        <img v-bind:src="image">
      </div>
    </div>
    <div class="SpooferList__item-body">
      <p>
        <strong>Title:</strong> {{ title }}<br/>
        <strong>Description:</strong> {{ description }}<br/>
        <strong>Link:</strong> <a v-bind:href="url">{{ url }}</a>
      </p>
    </div>
  </li>
</template>

<script>
export default {
  name: 'SpooferItem',
  props: [
    'title',
    'description',
    'image',
    'url',
  ],
}
</script>

<style>
li {
  align-items:flex-start;
  display:flex;
  list-style:0 none;
  text-align:left;
}

li + li {
  border-top:1px solid rgba(0, 0, 0, 0.4);
  margin-top:15px;
  padding-top:15px;
}

.SpooferList__item-image {
  margin-right:1em;
}

.SpooferList__item-image-wrapper {
  align-items:center;
  display:flex;
  height:100px;
  text-align:center;
  width:100px;
}

.SpooferList__item-image-wrapper img {
  max-height:100%;
  max-width:100%;
}

.SpooferList__item-body {
  flex:1;
}
</style>

<template>
  <div class="SpooferListWrapper">
    <ul class="SpooferList">
      <SpooferItem
        v-for="(spooferItem, index) in spooferItems"
        :title="spooferItem.title"
        :description="spooferItem.description"
        :image="spooferItem.image"
        :index="index"
        :key="spooferItem.id"
      />
    </ul>
  </div>
</template>

<script>
import SpooferItem from './SpooferItem'

export default {
  name: 'SpooferList',
  components: {
    SpooferItem,
  },
  props: [
    'spooferItems',
  ],
}
</script>

<style scoped>
.SpooferListWrapper {
  background-color:#f1f1f1;
  border-top:1px solid rgba(0, 0, 0, 0.3);
  margin:30px auto 0;
  max-width:500px;
  padding:20px;
}
</style>

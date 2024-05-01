<template>
  <div class="vertical-list">
    <div v-for="(item, index) in items" :key="item" class="vertical-item">
      <HorizontalList :index="index" :length="item.length" />
    </div>
  </div>
</template>

<script>
import HorizontalList from './HorizontalList.vue';

export default {
  components: {
    HorizontalList
  },
  props: {
    items: Array
  }
}
</script>

<style>
.vertical-list {
  display: flex;
  flex-direction: column;
}

.vertical-item {
  margin-bottom: 20px;
}
</style>

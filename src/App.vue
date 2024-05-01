<template>
  <div id="app">
    <VerticalList :items="lists" />
  </div>
</template>

<script>
import VerticalList from './components/VerticalList.vue';

export default {
  components: {
    VerticalList
  },
  data() {
    return {
      lists: Array.from({ length: Math.floor(Math.random() * 100) + 100 }, () => Array.from({ length: Math.floor(Math.random() * 10) + 10 }))
    };
  }
}
</script>

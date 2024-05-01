<template>
  <div class="horizontal-list">
    <div
      v-for="number in numbers"
      :key="number"
      class="square"
    >
      {{ number }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    index: Number,
    length: Number
  },
  data() {
    return {
      numbers: Array.from({ length: this.length }, () => Math.floor(Math.random() * 100))
    };
  },
  mounted() {
    setInterval(() => {
      const index = Math.floor(Math.random() * this.length);
      this.numbers.splice(index, 1, Math.floor(Math.random() * 100));
    }, 1000);
  }
}
</script>

<style>
.horizontal-list {
  display: flex;
}

.square {
  width: 50px;
  height: 50px;
  border: 1px solid black;
  border-radius: 10px;
  margin-right: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: transform 0.3s ease;
}

.square:hover {
  cursor: pointer;
  transform: scale(0.8);
}
</style>

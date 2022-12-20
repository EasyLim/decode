<script setup>
import { ref } from 'vue';
const props = defineProps(['secret', 'letter']);
const letter = ref(props.letter);
</script>

<template>
  <div>
    <input
      type="text"
      v-if="![' ', '.', '4'].includes(props.secret)"
      v-model="letter"
    />
    <span>{{ props.secret }}</span>
  </div>
</template>

<style scoped>
div {
  display: inline-flex;
  flex-direction: column;
  justify-content: end;
  width: 15px;
  height: 20px;
  margin: 2px;
  align-items: center;
}
input {
  width: 10px;
  text-align: center;
}
</style>

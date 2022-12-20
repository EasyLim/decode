<script setup>
import Letter from './Letter.vue';
import { ref } from 'vue';
const props = defineProps(['secret']);

const letters = {};
for (let letter of props.secret) {
  letters[letter] = ref('');
}
</script>

<template>
  <Letter
    v-for="letter in props.secret"
    :secret="letter"
    :letter="letters[letter]"
  ></Letter>
</template>

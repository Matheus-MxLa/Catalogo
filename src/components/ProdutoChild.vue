<script setup>
 defineProps(['id', 'nome', 'preco', 'categoria'])
 import ButtonChild from './ButtonChild.vue';
</script>

<template>
  <li>
    {{ nome }} - R$ {{ preco }} - ({{ categoria }})
    <ButtonChild>Corrigir Preço</ButtonChild>
  </li>
</template>

<style scoped>

</style>

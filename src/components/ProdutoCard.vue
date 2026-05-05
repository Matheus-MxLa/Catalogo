<script setup>
  //import { ref } from 'vue';
  defineProps (['id', 'nome', 'preco', 'imagem', 'categoria']);
  import ButtonChild from './ButtonChild.vue';
import { formataPreco } from '@/utilis/produtoUtils';
</script>

<template>

  <div class="produto-card">
    <div>
      <h2>{{ nome }}</h2>
      <p>Preço: {{ formataPreco(preco) }}</p>
    </div>
    <div>
      <img :src="imagem" class="produto-imagem"/>
    </div>
    <ButtonChild>Editar</ButtonChild>
  </div>
</template>

<style scoped>
.produto-card {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border: 1px solid #ccc;
  padding: 16px;
  margin-bottom: 16px;
}

img {
  width: 5vw;
  height: 5vw;
  object-fit: cover;

}
</style>

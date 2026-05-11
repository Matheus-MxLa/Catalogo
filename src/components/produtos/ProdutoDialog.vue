<script setup>
  import { ref } from 'vue'
  const props = defineProps(['nome', 'id', 'preco', 'categoria']);
  defineEmits(['corrigirpreco', 'fechar']);
  import ButtonChild from '../ButtonChild.vue';
  import { formataPreco } from '@/utilis/produtoUtils';
  const novopreco = ref(0);
  novopreco.value = props.preco
</script>

<template>
  <div class="overlay">
    <div class="produto-dialog">
      <h2>{{ props.nome }}</h2>
      <p>Preço: {{ formataPreco(props.preco) }}</p>
      <p>Categoria: {{ props.categoria }}</p>
      <input type="number" v-model.number="novopreco">
      <ButtonChild @clique="$emit('corrigirpreco', id, novopreco)">CorrigirPreço</ButtonChild>
      <ButtonChild @clique="$emit('fechar')">Cancelar</ButtonChild>
    </div>
  </div>
</template>

<style scoped>
.produto-dialog {
  border: 1px solid #ccc;
  padding: 24px;
  margin-top: 16px;
  background-color: white;
  border-radius: 8px;
  min-width: 320PX;
}
.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgb(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}
</style>

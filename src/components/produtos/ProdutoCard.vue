<script setup>
  import { ref } from 'vue';
  const mostrarDialog = ref(false);
  defineProps (['id', 'nome', 'preco', 'imagem', 'categoria']);
  const emit = defineEmits(['altualizarpreco'])
  import ButtonChild from './ButtonChild.vue';
  import ProdutoDialog from './ProdutoDialog.vue';
  import { formataPreco } from '@/utilis/produtoUtils';

  function corrigirPreco(id, preco) {
    emit('altualizarpreco', id), preco;
    mostrarDialog.value = false;

  }
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
    <ButtonChild @clique="mostrarDialog = true">Editar</ButtonChild>
    <ProdutoDialog v-if="mostrarDialog"
    :nome="nome"
    :id="id"
    :preco="preco"
    :categoria="categoria"
    @fechar="mostrarDialog = false"
    />
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

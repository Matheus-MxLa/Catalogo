<script setup>
  import { RouterView } from 'vue-router';
  import AppHeader from './components/AppHeader.vue';
</script>

<template>
  <AppHeader/>
  <main>
    <RouterView />
  </main>

  <!--
    <div class="container">
    <h1>Catálogo de Produtos</h1>
    <div>
      <ul>
        <ProdutoChild v-for="produto in produtos"
            :key="produto.id" :id="produto.id"
            :nome="produto.nome" :preco="produto.preco"
            :categoria="produto.categoria"
            @corrigirpreco="corrigirPreco"
          >
        </ProdutoChild>
      </ul>
    </div>
    <div v-show="alterando">
      <label>Preço</label>
      <input type="number" v-model.number="preco">
      <ButtonChild @clique="salvarPreco()">Salvar</ButtonChild>
    </div>
  </div>
  -->
</template>

<style scoped>

</style>

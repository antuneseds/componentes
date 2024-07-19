<script setup>
  import {ref} from 'vue'
  import ProductList from './components/ProductList.vue';
  import ProductAdd from './components/ProductAdd.vue';

  const produtos = ref([
    {id:1, nome: 'Produto 1', preco: 'R$20,50'},
    {id:2, nome: 'Produto 2', preco: 'R$120,50'},
    {id:3, nome: 'Produto 3', preco: 'R$220,50'},
    {id:4, nome: 'Produto 4', preco: 'R$320,50'}
  ])

  function remove (id) {
    const index = produtos.value.findIndex((produto) => produto.id === id);
    produtos.value.splice(index, 1);
  }
</script>

<template>
  <h1>Meus produtos</h1>
  <product-list :produtos="produtos" @remove="remove"/>
 
</template>

<style scoped>
   table {
    width: 50%;
    border-collapse: collapse;
  }

  th,
  td {
    border: 1px solid gray;
    padding: 10px;
  }

  th {
    background-color: lightgray;
  }

  tr {
    text-align: center;
  }

  tr i {
    cursor: pointer;
    font-size: larger;
  }
</style>

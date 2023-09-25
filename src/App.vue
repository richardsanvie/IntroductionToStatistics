<script setup>
import { reactive } from 'vue';

  const items = reactive({
    nome: ['Ye','Jonas'],
    nomeAAdicionar:''
  })

  function adicionaNome(){
    if(items.nomeAAdicionar.length>=3){
      items.nome.push(items.nomeAAdicionar)
    } else{
      alert('adicione mais caracteres')
    }
  }


</script>

<template>
  <div class="container d-flex align-items-center vh-100">
    <h2>nameRecords</h2>
    <div class="container bg-light rounded-2  align-content-center p-3" style="width: 500px;">
    <ul class="m-0">
      <li v-for="ListNames in items.nome ">{{ ListNames }}</li>
    </ul>
    <div class="container-fluid d-flex mt-2">
      <div class="form-floating col-9">
        <input type="text" class="form-control" placeholder="" @keyup="evento=>items.nomeAAdicionar=evento.target.value">
        <label for="">Name</label>
      </div>
      <button v-if="items.nomeAAdicionar.length>=3" class="btn btn-success col-3" @click="adicionaNome()">Cadastrar</button>
      <button v-else class="btn btn-outline-danger col-3" style="font-size: 10px;">Adicione mais caracteres</button>
    </div>
  </div>
  </div>
</template>

<style scoped>

</style>

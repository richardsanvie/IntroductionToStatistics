<script setup>
import { reactive } from 'vue';

const items = reactive({
  nome: ['Ye', 'Jonas'],
  nomeAAdicionar: ''
})

function adicionaNome() {
  if (items.nomeAAdicionar.length >= 3) {
    items.nome.push(items.nomeAAdicionar)
  } else {
    alert('adicione mais caracteres')
  }
}


</script>

<template>
  <div class="content">
    <div class="containerFluid">
      <div class="">
        <h2>nameRecords</h2>
      </div>
      <div class="bg-light rounded-2 p-3">
        <ul class="m-0">
          <li v-for="ListNames in items.nome ">{{ ListNames }}</li>
        </ul>
        <div class="container-fluid d-flex mt-2 p-0">
          <div class="form-floating col-8">
            <input type="text" class="form-control" placeholder=""
              @keyup="evento => items.nomeAAdicionar = evento.target.value">
            <label>Name</label>
          </div>
          <button v-if="items.nomeAAdicionar.length >= 3" class="btn btn-success col-4" style="margin-left: 10px;"
            @click="adicionaNome()">Cadastrar</button>
          <button v-else class="btn btn-outline-danger col-4" style="font-size: 10px; margin-left: 10px;">Adicione mais
            caracteres</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.content {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
}

.containerFluid {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  width: 40%;
}

.bg-light {
  margin-left: 15px;
}

@media screen and (max-width:767px) {
  .containerFluid {
    display: block;
    width: 100%;
  }

  .bg-light {
    margin-left: 0;
  }

  h2 {
    margin-left: 10px;
    font-size: 45px;
  }

  .content {
    padding: 10px;
  }
}
</style>

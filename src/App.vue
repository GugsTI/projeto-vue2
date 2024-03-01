<script setup>
  import { ref } from 'vue';

  const nome = (ref(prompt("Informe seu nome:")));
  const idade = (ref(prompt("Informe sua idade:")));
  const contador = ref(0);

  function incrementar() {
    contador.value++;
  }

  function decrementar() {
    if (contador.value > 0) {
      contador.value--;
    }
  }

  function reiniciar() {
    contador.value = 0;
  }

  function inverterTextoEmMaiusculo(texto) {
    return texto.split('').reverse().join('').toUpperCase();
  }
</script>

<template>
  <div class="info">
    <h2 class="devInfo">INFORMAÇÕES</h2>
    <p class="edit">Nome: {{ nome }} </p>
    <p class="edit">Idade:{{ idade }} anos</p>
    <hr />
    <p class="edit">
      Para completar 50 anos faltam: {{ 50 - idade }} anos
    </p>
    <p class="edit">O nome tem {{ nome.length }}  caracteres</p>
    <p class="edit">
      O nome invertido em maiúscula é:{{
      inverterTextoEmMaiusculo(nome) }} 
    </p>
    <p>
      <button class="botao1"><a href="https://gugscontador.surge.sh/"></a>Contador1.0</button>
    </p>
  </div>
  <br>
  <div class="contador">
    <h2 class="devCon">Contador</h2>
    <p>Valor: {{ contador }}</p>
    <button class="botao" @click="incrementar">Incrementar</button>
    <button class="botao" @click="decrementar">Decrementar</button>
    <button class="botao" @click="reiniciar">Reiniciar</button>
    <div
    >
    <br>
      <p class="Maior"   v-if="contador > 10">Valor maior que 10</p>
      <p class="Menor" v-else>Valor menor que 10</p>
    </div>
  </div>
</template>

<style scoped>
.botao1{
  background-color:chartreuse; 
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  border-radius: 30px;
}
.edit{
  font-family: 'Times New Roman', Times, serif;
}
.devInfo{
  color:chartreuse;
  font-family: 'Times New Roman', Times, serif;
  
}
.Menor{
  color: red;
}
.Maior{
  color: cornflowerblue;
}

.devCon{
  color: cornflowerblue;
}
.info{
  background-color: #000000;
  text-align: center;
  font-size: 35px;
  color: white;
  border-radius: 50px;
  width: 200%;
  height: 500px;
  margin-bottom: 100%;
margin-left: 30px;
margin-top: 25px;
box-shadow: 10px 10px 5px 12px chartreuse;
}

.contador{
  font-family:monospace;
  margin-top: 100%;
  background-color: #000000;
  text-align: center;
  font-size: 35px;
  color: white;
  border-radius: 50px;
  width: 200%;
  height: 400px;
  margin-top: -93.2%;
  margin-left: 25px;
  box-shadow: 10px 10px 5px 12px cornflowerblue;
}

  .botao{
    background-color:cornflowerblue; 
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  border-radius: 30px;
  }


  
</style>
<script setup>
import { ref, onMounted } from 'vue'

const contador = ref(0)

function incrementarContador() {
  contador.value++
}
function decrementarContador() {
  if (contador.value >0) {
  contador.value--
  }
}
function zerarContador(){
  contador.value = 0
}



onMounted(() => {
  console.log(`O valor inicial do contador é ${contador.value}.`)
})

const nome = 'victor'
    const idade = 16

    function inverter(texto) {
        return texto.split('').reverse().join('')
    }

    function inverterMaiusculo(texto) {
      const invertido = inverter(texto)
      return invertido.toUpperCase()
    }

    function saudacao() {
        return `Olá, ${nome}!`
    }
</script>

<template>
  <div class="info">
        <h1>Exemplo 1 - Mostrando informações na tela</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ inverter(nome) }} </p>
        <p>O nome invertido em maiúsculas é: {{ inverterMaiusculo(nome) }}</p>
        <hr />
        <p> Exemplo de saudação usando função</p>
        <p> {{ saudacao() }}  </p>
    </div>
    <div class="info">
      Contador: {{ contador }}
      <button @click=" contador++">+</button>
      <button @click=" contador--">-</button>
      <div v-if="contador > 10">O contador é maior que 10</div>
      <div v-else-if="contador < 10">O contador é menor que 10</div>
      <div v-else>O contador é 10</div>
      <hr />
      <div v-if="contador % 2 === 0"> É par</div>
      <div v-else>É impar</div>
    </div>
</template>

<style scoped>
button {
  font-weight: bold;
}

.info {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
  margin: 0px 20px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}
</style>
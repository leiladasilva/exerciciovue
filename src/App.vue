<script setup>
import { ref } from 'vue';

const nome = ref('leila');
const idade = ref(17);
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
        <h2>Informações</h2>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }} anos</p>

        <p>
            Para completar 50 anos faltam: {{ 50 - idade }} anos
        </p>
        <p>O meu nome tem {{ nome.length }} caracteres</p>
        <p>
            O nome invertido em maiúscula é: {{
                inverterTextoEmMaiusculo(nome) }}
        </p>
        <span style='font-size:100px;'>&#128147;</span>
    </div>
    <div class="contador">
        <h2>Contador</h2>
        <p>Valor: {{ contador }} </p>
        <button @click="incrementar">Incrementar</button>
        <button @click="decrementar">Decrementar</button>
        <button @click="reiniciar">Reiniciar</button>
        <div :style="{ backgroundColor: contador > 10 ? 'purple' : 'black' }">
            <p v-if="contador > 10">Valor maior que 10</p>
            <p v-else>Valor menor que 10</p>
        </div>
    </div>
</template>

<style scoped>
.info,
.contador {
    margin-top: 0;
    margin-bottom: 0;
    margin: 40px;
    background-color: rgb(207, 73, 131);
    padding: 20px 30px;
    color: rgb(183, 210, 219);
    border-radius: 50px;

}

button {
    margin: 5px;
    padding: 10px;
    border: 0px;

    border-radius: 100px;
    background-color: rgb(0, 0, 0);
    color: rgb(255, 254, 254);
    font-weight: bold;
    cursor: pointer;
}

button:hover {
    background-color: rgb(197, 71, 176);
}

div {
    margin: 10px 0;
    padding: 10px;
    border-radius: 5px;
    color: white;
    font-weight: bold;
}

h2 {
    color: black;
}
</style>
<script setup lang="ts">
import { reactive } from 'vue';

const state = reactive({
    title: 'Calculadora com Vue.js App',
    signal: '',
    numbers: (a: number, b: number) => a + b,
    num_A: 0,
    num_B: 0,
    tag_select: ''
})

// const getSinal = () => {

//     const tag_select = document.querySelector('select')?.value;

//     console.log(tag_select);


//     const { signal } = state;

//     switch (signal) {
//         case '+':
//             alert('Soma');
//             break;
//         case '-':
//             alert('Subtração');
//             break;
//         case '*':
//             alert('Multiplicação');
//             break;
//         case '/':
//             alert('Divisão');
//             break;
//         default:
//             console.log('Nenhum valor selecionado');
//             break;
//     }
//     return tag_select;

// }

</script>

<template>

    <header class="container text-center my-4">

        <h1>
            <p>{{ state.title }}</p>
        </h1>
        <img alt="Vue logo" src="./assets/calculator.svg">

    </header>

    <div class="container calc text-center">
        <form v-on:submit="" action="">
            <p><input class="col-auto form-control" type="number" v-model.number="state.num_A" /></p>
            <p><input class="form-control" type="number" v-model.number="state.num_B" /></p>
            <!-- <p>Soma: {{ state.numbers(state.num_A, state.num_B) }}</p>   -->

            <!-- <div class="btn-group-lg mb-1" role="group" aria-label="Basic example">
                <button class="btn btn-outline-primary" type="button" @click="state.signal = '+'">+</button>
                <button class="btn btn-outline-primary" type="button" @click="state.signal = '-'">-</button>
                <button class="btn btn-outline-primary" type="button" @click="state.signal = '*'">*</button>
                <button class="btn btn-outline-primary" type="button" @click="state.signal = '/'">/</button>
            </div> -->

            <div class="btn-group-lg" role="group" aria-label="Basic radio toggle button group">
                <input @click="state.signal = '+'" type="radio" class="btn-check" name="btnradio" id="btnradio1"
                    autocomplete="off" checked>
                <label for="btnradio1" class="btn btn-outline-primary">+</label>
                <input @click="state.signal = '-'" type="radio" class="btn-check" name="btnradio" id="btnradio2"
                    autocomplete="off">
                <label for="btnradio2" class="btn btn-outline-primary">-</label>
                <input @click="state.signal = '*'" type="radio" class="btn-check" name="btnradio" id="btnradio3"
                    autocomplete="off">
                <label for="btnradio3" class="btn btn-outline-primary">*</label>
                <input @click="state.signal = '/'" type="radio" class="btn-check" name="btnradio" id="btnradio4"
                    autocomplete="off">
                <label for="btnradio4" class="btn btn-outline-primary">/</label>
            </div>

            <!-- <div class="oper d-flex justify-content-evenly align-items-center flex-row-reverse">
                <select @change="(e: Event) => state.signal = (e.target as HTMLSelectElement).value" class="btn-group"
                    role="group" aria-label="Basic radio toggle button group" name="" id="">
                    <option class="btn" value="+">+</option>
                    <option class="btn" value="-">-</option>
                    <option class="btn" value="*">*</option>
                    <option class="btn" value="/">/</option>
                    <option selected class="btn" value=" "></option>
                </select>
                <p class="my-0">Operação:</p>
            </div> -->
        </form>


        <p>Resultado:
            <span v-if="state.signal === '+'"> {{ state.num_A + state.num_B }} </span>
            <span v-else-if="state.signal === '-'">{{ state.num_A - state.num_B }}</span>
            <span v-else-if="state.signal === '*'">{{ state.num_A * state.num_B }}</span>
            <span v-else-if="state.signal === '/'">{{ state.num_A / state.num_B }}</span>
            <span v-else>Selecione uma operação</span>
        </p>

    </div>
</template>

<style scoped>
.calc input {
    width: 100%;
    font-size: 20px;
    text-align: center;
}

.btn-group button {
    width: 40px;
    height: 40px;
    margin: 5px;
    font-size: 20px;
    font-weight: bold;
}

.calc {
    width: 250px;
    margin: 0 auto;
    font-size: 20px;
}

/* .oper p {
    margin:0;
} */
</style>
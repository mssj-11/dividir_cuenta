<script setup>
import { ref } from 'vue';
import { store, calculate } from '../store/store';

//  Estados reactivos
const total = ref(0);
const tip = ref(0);
const people = ref(0);


//  Evento para el formulario
function handleSubmit(){
    store.params.total = total;
    store.params.tip = tip;
    store.params.people = people;
    calculate();
}
</script>


<template>
    <form class="form" @submit.prevent="handleSubmit">
        <div class="card mt-5 p-4 bg-light">
        <h2 class="mb-4 mt-4 p-2 bg-success text-center text-white">Dividir Cuenta</h2>
        <div class="form-container">
            <div class="mb-3">
                <label for="total" class="form-label">Total</label>
                <input type="number" class="form-control" v-model="total" required>
            </div>

            <div class="mb-3">
                <label for="tip" class="form-label">Tip</label>
                <input type="number" class="form-control" v-model="tip" required>
            </div>

            <div class="mb-3">
                <label for="people">People</label>
                <input type="number" class="form-control" v-model="people" required>
            </div>

            <div class="mb-3">
                <button type="submit" class="btn btn-primary">Calcul</button>
            </div>
        </div>
    </div>
    </form>
</template>


<style scoped></style>
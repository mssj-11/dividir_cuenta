<script setup>
import { defineProps, ref } from 'vue';
import { pay } from '../store/store';

const props = defineProps(['id', 'numberOfPerson', 'totalPerPerson', 'paid']);
let paid = ref(false);


function handleChange(e){
    paid = e.target.checked;

    pay(props.id, paid);
}
</script>

<template>
    <div :class="['person', props.paid ? 'person-paid' : 'person-no-paid']" class="card bg-dark text-white">
        <div class="mt-3 fw-bold p-1 bg-primary">
            Person {{ props.numberOfPerson }}
        </div>

        <div>
            {{
            new Intl.NumberFormat('en-US', {
                style: "currency",
                currency: "USD"
            }).format(props.totalPerPerson)
            }}
        </div>

        <div>
            <input type="checkbox" @change="handleChange">
            <label for="">Paid</label>
        </div>
    </div>
</template>

<style scoped>
.person{
    margin: 12px;
    height: 150px;
    align-items: center;
    font-size: 22px;
}
</style>
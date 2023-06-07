<script setup>
import { store, getGrandTotal } from '../store/store';
import Label from './Label.vue';
import Person from '../components/Person.vue';
</script>

<template>
    <div class="no-items mt-5" v-if="store.people.length === 0"><h3>No items</h3></div>
    <div class="mt-5" v-if="store.people.length > 0">
        <div class="header fw-bold p-3 bg-primary text-white">
            <div>
                <Label title="Total + Tip: " :value="getGrandTotal()" />
            </div>

            <div>
                <Label title="Remaining: " :value="store.params.remaining" />
            </div>
        </div>

        <div class="people-container">
                <Person 
                    v-for="person in store.people" 
                    :key="person.id"
                    :id="person.id" 
                    :number-of-person="person.numberOfPerson" 
                    :total-per-person="person.totalPerPerson" 
                    :paid="person.paid" 
                />
        </div>
    </div>
</template>

<style scoped>
.people-container{
    display: grid;
    grid-template-columns: auto;
    grid-template-rows: auto;
}
</style>
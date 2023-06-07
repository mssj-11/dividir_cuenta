<script setup>
import InputForm from './InputForm.vue';
import PeopleView from './PeopleView.vue';
</script>

<template>
    <div class="container">
        <div class="col-4"><InputForm /></div>
        <div class="col-8 m-2"><PeopleView /></div>
    </div>
</template>

<style scoped>
.container{   display: flex;  }
</style>
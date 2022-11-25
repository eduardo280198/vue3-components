<script setup>
    import {ref} from 'vue';

    const counter = ref(0);

    const increment = () => counter.value++;

    defineProps(['texto']);
</script>

<template>
    <button @click="increment">{{texto}} {{counter}}</button>
</template>

<style></style>
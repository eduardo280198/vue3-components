<script setup>
defineProps(["inicio", "final", "maxLength"]);

</script>

<template>

    <div class="btn-group" role="group" aria-label="Basic example">
        <button
            @click="$emit('prev')"
            type="button"
            class="btn btn-outline-primary"
            :disabled = "inicio === 0"
        >Previus {{inicio}}</button>
        
        <button 
            @click="$emit('next')"
            type="button"
            class="btn btn-outline-primary"
            :disabled = "final === maxLength"
        >Next {{final}}</button>
    </div>
</template>
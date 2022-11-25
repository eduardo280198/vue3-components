<script setup>
    defineProps(['title', 'id', 'body', 'colorText']);
</script>

<template>
    <div class="card">
        <div class="card-body">
            <h5 
                class="card-title"
                :class="`text-${colorText}`"
            >{{id}} - {{title}}</h5>
            <p>{{body}}</p>
        </div>
    </div>
</template>
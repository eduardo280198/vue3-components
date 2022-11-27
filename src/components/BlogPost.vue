<script setup>
    // defineProps(['title', 'id', 'body']);

    defineProps({
        title: String,
        id: Number,
        body:{
            type: String,
            default: "Sin descripción",
        },
    });
</script>

<template>
    <div class="card">
        <div class="card-body">
            <h5 
                class="card-title"
            >{{id}} - {{title}}</h5>
            <p>{{body}}</p>

            <button
                @click="$emit('cambiarFavorito', title)"
                class="btn btn-outline-primary"
            >Favorito</button>
        </div>
    </div>
</template>
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

    const emit =defineEmits(['cambiarFavoritoPropiedad']);

    //emit('cambiarFavoritoPropiedad', title) <- Es mas controlable y puede ser llamado dentro de script
</script>

<template>
    <div class="card">
        <div class="card-body">
            <h5 
                class="card-title"
            >{{id}} - {{title}}</h5>
            <p>{{body}}</p>

            <button
                @click="emit('cambiarFavoritoPropiedad', title)"
                class="btn btn-outline-primary"
            >Favorito</button>
        </div>
    </div>
</template>
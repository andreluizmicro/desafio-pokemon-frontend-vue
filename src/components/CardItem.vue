<script setup>
    const pokemon = defineProps(['info'])
    
</script>

<template>
    <div class="card">
        <p>{{ pokemon.info.name }}</p>
        <router-link :to="'/details/'+pokemon.info.id">Detalhes</router-link>
    </div>
</template>

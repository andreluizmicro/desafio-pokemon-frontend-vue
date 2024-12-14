<script setup>
    const pokemon = defineProps(['info'])

    const urlDetails = `http://localhost:8000/api/v1/pokemons/${pokemon.info.id}`
    
</script>

<template>
    <div>
        <div class="card">
            <p>{{ pokemon.info.name }}</p>
            <a :href="urlDetails">
                <button class="btn-details">Detalhes</button>    
            </a>
        </div>
    </div>
</template>

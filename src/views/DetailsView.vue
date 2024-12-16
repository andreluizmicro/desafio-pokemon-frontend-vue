<script setup>
import { onMounted, reactive} from 'vue';
import {useRouter} from "vue-router";
    
    let pokemon = reactive();
    
    const router = useRouter()

    const id = router.currentRoute.value.params.id

    onMounted(() => {
        fetch(`http://localhost:8000/api/v1/pokemons/${id}`)
        .then(res => res.json())
        .then(res => pokemon = res.data)
    });

</script>

<template>
    <div class="pokemon-details">
        <h1>{{ pokemon.name }}</h1>
        Tipo: 
        <li v-for="pokemon in pokemon.type" :key="pokemon.type">
        {{ pokemon.name }}
      </li>
      <p>Peso: {{ pokemon.height }}</p>
      <p>Altura: {{ pokemon.weight }}</p>
    </div>
</template>
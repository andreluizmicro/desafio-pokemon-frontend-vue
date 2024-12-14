<script setup>
    import { onMounted, reactive} from 'vue';
    import CardItem from '@/components/CardItem.vue';
    
    let pokemons = reactive();

    onMounted(() => {
        fetch("http://localhost:8000/api/v1/pokemons?offset=2&limit=5")
        .then(res => res.json())
        .then(res => pokemons = res);
    })    
</script>

<template>
  <div class="section">
    <CardItem v-for="pokemon in pokemons.data.items" :key="pokemon.name" :info="pokemon" />
  </div>
</template>
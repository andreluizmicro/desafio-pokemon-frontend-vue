<script setup>
    import { onMounted, reactive} from 'vue';
    import CardItem from '@/components/CardItem.vue';
    
    let pokemons = reactive();

    onMounted(() => {
        fetch("http://localhost:8000/api/v1/pokemons?offset=2&limit=8")
        .then(res => res.json())
        .then(res => pokemons = res);
    })    
</script>

<template>

  <div class="section">
    <CardItem v-for="pokemon in pokemons.data.items" :key="pokemon.name" :info="pokemon"/>
  </div>

  <div class="info-list">
    <a href="#" class="link-page">1</a>
    <a href="#" class="link-page">2</a>
    <a href="#" class="link-page">3</a>
  </div>
</template>
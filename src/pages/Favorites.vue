<template>
    <h2 class="text-3xl font-bold mb-8">Мои закладки</h2>
    <CardList
    :items="favorites"
    is-favorites
    @add-to-cart="onClickAddPlus"
    />
</template>

<script setup>
import CardList from "@/components/CardList.vue";
import { onMounted, ref } from "vue";
import axios  from 'axios'

const favorites = ref([]);

onMounted(async() => {
    try {
        const {data} = await axios.get(`https://76cf88875a4206d9.mokky.dev/favorites?_relations=items`)

        favorites.value = data.map((obj) => obj.item)
    } catch(err) {
        console.log(err)
    }
});
</script>

<style lang="scss" scoped>

</style>
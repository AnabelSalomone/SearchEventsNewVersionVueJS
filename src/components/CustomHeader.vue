<template>
    <div class="container">
        <div class="title">
            Search Events
        </div>
        <div class="favorites" @click="seeFavorites">
           <p v-if="choice === 'search'">Favorites</p>
           <p v-if="choice === 'favorites'">Search</p>
        </div>
    </div>
</template>

<script>
export default {
    name: "customHeader",
    props: ["choice"],
    methods: {
        seeFavorites() {
            this.$emit("see-favorites");
        }
    }
}
</script>

<style scoped>
.container {
    display: flex;
    width: 100vw;
    margin: 0;
    background-color: navy;
    justify-content: space-between;
    align-items: center;
}
.title{
    color: white;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 3rem;
}
.favorites {
    color: white;
    padding-right: 1rem;
}
</style>
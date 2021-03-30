<template>
    <div>
        Search: <input type="text" v-model="keyword" @keyup="search()" />
    </div>
</template>

<script>
export default {
    data () {
        return{
            keyword: ""
        }
    },
    methods: {
        search() {
            this.$emit('search-event', this.keyword);
        }
    }
}
</script>

<style scoped>
div {
    font-family: Arial, Helvetica, sans-serif;
    margin: 1rem;
    text-align: center;
    }
</style>
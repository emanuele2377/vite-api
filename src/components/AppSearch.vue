<script>
import { store } from "../store.js" //state management


export default {
    name: "AppSearch",
    data() {
        return {
            store
        }
    },
    methods: {
        search() {
            console.log("Cerca: ", this.store.searchString);
            this.$emit("search");
        }
    },
    mounted() {

    }
}
</script>

<template>
    <div>
        <input placeholder="Cerca..." v-model="store.searchString" @keyup.enter="$emit('search')">
        <button @click="search">Cerca</button>
    </div>
</template>

<style scoped></style>
<script>

export default {
    props: ["arrayGenerato"]

}
</script>

<template>
    <div class="container">
        <div v-for="elemento in arrayGenerato">
            <div class="card2">
                Nome: <br>{{ elemento.name }}
                Citta: <br> {{ elemento.city }}
            </div>
        </div>
    </div>
</template>

<style scoped>
.container {
    display: flex;
    flex-direction: row;
}
</style>

<style scoped>
.card2 {
    background-color: #66D3FA;
    margin: 2%;
    height: 12rem;
    text-align: center;
}
</style>

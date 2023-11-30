<script>

export default {
    props: ["arrayGenerato"]

}
</script>

<template>
    <div v-for="elemento in arrayGenerato">
        <span>{{ elemento.name }}</span>
        <span> {{ elemento.city }}</span>
    </div>
</template>

<style scoped></style>

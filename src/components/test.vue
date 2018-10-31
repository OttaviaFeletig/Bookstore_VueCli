<template>
    <h3>I am {{myName}} and I am {{myAge}} years old</h3>

    <p v-for="(num, index) num in number" :key="index">{{ num }}</p>

</template>

<script>
export default {
    name: "test",
    props: ['myName', 'myAge', 'number']
}
</script>


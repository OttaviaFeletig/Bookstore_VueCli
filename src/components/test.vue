<template>
    <div>
        <h3>I am {{myName}} and I am {{myAge}} years old</h3>
        <p v-for="(item, index) in array" :key="index">{{ item }}</p>
        <p v-if="number > 2">{{number}}</p>
        <p v-else>The number is too small</p>
    </div>
</template>

<script>
export default {
    name: "Test",
    props: ['myName', 'myAge', 'array', 'number']
}
</script>


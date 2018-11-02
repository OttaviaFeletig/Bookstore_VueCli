<template>
    <div class="one_book">
        <div class="d-flex justify-content-start w-20">
            <img class="img-fluid" :src=oneBook.cover alt="books-cover">
        </div>
        <div class="back w-50">
            <h2>{{oneBook.title}}</h2>
            <p>{{oneBook.description}}</p>
        </div>
        
    </div>
</template>

<script>
export default {
    name: 'oneBook',
    props: ['oneBook']
}
</script>

<style>
    .back{
        text-align: justify;
    }
</style>

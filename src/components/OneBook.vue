<template>
    
        <div class="one_book w-25 h-auto">
            <div class="front">
                <img class="img_dimension" :src=oneBook.cover alt="books-cover">
            </div>
            <div class="back">
                <h3>{{oneBook.title}}</h3>
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
    .img_dimension{
        width: 100%;
        height: auto; 
    }
    .one_book{
        display: flex;
        flex-wrap: wrap;
    }
</style>

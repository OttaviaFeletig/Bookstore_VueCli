<template>
    <div class="book_container w-25">
        <div ontouchstart="this.classList.toggle('hover');">
        <div class="one_book w-100 h-auto d-flex flex-wrap">
            <div class="front">
                <img class="img_dimension" :src=oneBook.cover alt="books-cover">
            </div>
            <div class="back">
                <h3>{{oneBook.title}}</h3>
                <p>{{oneBook.description}}</p>
                <button id="show-modal" class="btn btn-dark w-100" @click="showModal = true">More Info</button>
            </div> 
            
              
            
          

        </div>
        </div>
          <Modal v-if="showModal" @close="showModal = false">
              
                    <img slot="body" :src=oneBook.detail alt="Detail" class="img_modal">
                </Modal>
        </div>
    
</template>

<script>

import Modal from '@/components/Modal.vue'
export default {
    name: 'oneBook',
    props: ['oneBook'],
    data(){
        return {
            showModal: false
        }
    },
    components: {
        Modal
    },
    created(){
        
    },
    methods:{
    }
}
</script>

<style>

 .book_container:hover .one_book,
.book_container:hover .one_book {
        transform: rotateY(180deg);
}
.one_book {
    transition: 0.6s;
    transform-style: preserve-3d;  
}

.front, .back {
    backface-visibility: hidden;
}

.front {
    z-index: 2;
    transform: rotateY(0deg);
}

.back {
    transform: rotateY(180deg);
    padding: 20px;
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0%;
    text-align: initial;
    background-color: lightgray;
    }
.back p {
    text-align: justify;
}

.img_dimension{
        width: 100%;
        height: auto; 
    }

.back h3{
    font-size: 1.4em;
    font-weight: bold;
}

.img_modal{
    width: 500px;
}

</style>

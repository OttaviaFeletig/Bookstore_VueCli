<template>
    
        <div class="one_book w-25 h-auto">
            <div class="front">
                <img class="img_dimension" :src=oneBook.cover alt="books-cover">
            </div>
            <div class="back">
                <h3>{{oneBook.title}}</h3>
                <p>{{oneBook.description}}</p>
                <button type="button" class="btn" name="more_info" @click="showModal = true"
                data-toggle="modal" data-target="#modalBooks">More Info</button>
            </div> 
            
                <Modal v-if="showModal" @close="showModal = false">
                    <img :src=oneBook.detail alt="Detail" class="img_dimension">
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
    position: absolute;
    top: 0%;
    text-align: initial;
}
.back p {
    text-align: justify;
}

.img_dimension{
        width: 100%;
        height: auto; 
    }

</style>

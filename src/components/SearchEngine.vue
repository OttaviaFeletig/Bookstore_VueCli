<template>
 
        <div class="row">

            <img class="col-2 h-100 logo" src="../../book_icon.png" alt="logo">
            
            <h1 class="d-flex align-items-center mr-5 ml-3">Otta's Bookstore</h1>
            
            <div class="d-flex justify-content-end col align-items-center">

                <input id="search_bar" v-model="search" class="form-control" type="text" placeholder="Search...">
            
            </div>

            <p>{{search}}</p>
            
        </div>

</template>

<script>


import Books from '@/components/Books.vue'
import OneBook from '@/components/OneBook.vue'

export default {
    name: 'searchEngine',
    data() {
      return {
        search: ''
      }
    },
    components: {
        Books,
        OneBook
    },
    props: [],
        computed: {
            searchBar2(){
         if(this.search == "") {
           return books
         } else {
           console.log(this.search)
           return books.filter(x => x.title.toUpperCase().includes(this.search.toUpperCase())
           ||
           x.description.toUpperCase().includes(this.search.toUpperCase()))
         }
          
        } 
    },
}
</script>

<style>

</style>

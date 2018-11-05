<template>
  <div class="book_container d-flex flex-wrap" ontouchstart="this.classList.toggle('hover');">
    <OneBook 
      v-for="(book, index) in books"  
      :oneBook="book"
      :key="index"/>
  </div>
</template>

<script>

import OneBook from '@/components/OneBook.vue'
export default {
  name: 'books',
  props: ['books'],
  components: {
    OneBook
  }
/*   created() {
    getBookList();
  },
  methods: {
    getBookList: function() {
      console.log(books)
    }
  } */
}
</script>

<style>
     .one_book:hover,
     .one_book:hover {
        transform: rotateY(180deg);
}
</style>



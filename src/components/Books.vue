<template>
  <div class="book_container">
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


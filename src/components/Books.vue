<template>
  <div>
    <div class="d-flex flex-wrap w-100 justify-content-center">
      <OneBook v-for="(book, index) in books" :oneBook="book" :key="index" :allBooks="books" />
    </div>
  </div>
</template>

<script>
import OneBook from "@/components/OneBook.vue";
import Carousel from "@/components/Carousel.vue";
export default {
  name: "books",
  props: ["books"],
  components: {
    OneBook,
    Carousel
  },
  methods: {}
};
</script>

<style>
</style>



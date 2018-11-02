<template>
   <div id="app">

      <div v-if="isLoading">
        <p>Wait</p>
      </div>
      <div v-else class="container d-flex flex-wrap justify-container-center">
        <Books :books="books"/>
      </div>
  

  </div>
</template>

<script>

import Books from '@/components/Books.vue'

  export default {
    name: "app",
    data() {
      return {
        books: [],
        isLoading: true
      }
    },
    components: {
      Books
    },
/*     computed: {
      isLoadingFetch() {
        if(this.books.length == 0) {
          return true
        }else {
          return false
        }
      }
  }, */
    created() {
      this.getFetch()
    },
    methods: {
      getFetch: function () {
        fetch("https://api.myjson.com/bins/zyv02", {
            method: "GET"
          })
          .then(response => {
            return response.json();
          })
          .then(data => {
            this.books = data.books
            console.log(this.books)
            this.isLoading = false});
      }
    }
  };
</script>



<style>
  #app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  #nav {
    padding: 30px;
  }

  #nav a {
    font-weight: bold;
    color: #2c3e50;
  }

  #nav a.router-link-exact-active {
    color: #42b983;
  }
</style>
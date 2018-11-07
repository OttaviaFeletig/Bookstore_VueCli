<template>
   <div id="app" class="container m-5">

        <div class="row">

            <img class="col-2 h-100 logo" src="../book_icon.png" alt="logo">
            
            <h1 class="d-flex align-items-center mr-5 ml-3">Otta's Bookstore</h1>
            
            <div class="d-flex justify-content-end col align-items-center">

                <input id="search_bar" v-model="search" class="form-control" type="text" placeholder="Search...">
            
            </div>
            
        </div>

      <div v-if="isLoading">
        <p>Wait</p>
      </div>
      <div v-else class="d-flex flex-wrap justify-content-center w-100 mt-5">
        <Books :books="searchBar2"/>
      </div>
  

  </div>
</template>

<script>

import Books from '@/components/Books.vue'
import OneBook from '@/components/OneBook.vue'
/* import SearchEngine from '@/components/SearchEngine.vue' */

  export default {
    name: "app",
    data() {
      return {
        books: [],
        isLoading: true,
        search: ''
      }
    },
    components: {
      Books,
      OneBook
/*       SearchEngine */
    },
    computed: {
        searchBar2(){
         if(this.search == "") {
           return this.books
         } else {
           console.log(this.search)
           console.log(OneBook)
           return this.books.filter(x => x.title.toUpperCase().includes(this.search.toUpperCase())
           ||
           x.description.toUpperCase().includes(this.search.toUpperCase()))
         }
          
        } 
    },
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
            this.isLoading = false})
            .catch(error => alert(error));
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
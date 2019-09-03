<template>
  <div id="app" class="container-fluid mt-2 w-100">
    <div class="row d-flex justify-content-center w-100">
      <img class="col-2 h-100 logo" src="../book_icon.png" alt="logo" />
      <h1 class="d-flex align-items-center mr-5 ml-3">Otta's Bookstore</h1>
      <SearchEngine @value="getSearch" />
    </div>
    <div v-if="isLoading">
      <p>Wait</p>
    </div>
    <div v-else class="w-100 mt-5">
      <Books :books="searchBar" />
    </div>
  </div>
</template>

<script>
import Books from "@/components/Books.vue";
import OneBook from "@/components/OneBook.vue";
import SearchEngine from "@/components/SearchEngine.vue";

export default {
  name: "app",
  data() {
    return {
      books: [],
      isLoading: true,
      search: ""
    };
  },
  components: {
    Books,
    OneBook,
    SearchEngine
  },
  computed: {
    searchBar() {
      if (this.search == "") {
        return this.books;
      } else {
        return this.books.filter(
          x =>
            x.titulo.toUpperCase().includes(this.search.toUpperCase()) ||
            x.descripcion.toUpperCase().includes(this.search.toUpperCase())
        );
      }
    }
  },
  created() {
    this.getFetch();
  },
  methods: {
    getFetch: function() {
      fetch("https://api.myjson.com/bins/udbm5", {
        method: "GET"
      })
        .then(response => {
          return response.json();
        })
        .then(data => {
          this.books = data.books;
          this.isLoading = false;
        })
        .catch(error => alert(error));
    },
    getSearch: function() {
      this.search = event.target.value;
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
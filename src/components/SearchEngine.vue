<template>
  <div class="row w-50">
    <div class="d-flex col align-items-center">
      <input
        id="search_bar"
        class="form-control"
        type="text"
        placeholder="Search..."
        v-on:input="handleChange($event)"
        v-bind:value="value"
      />
    </div>
    <p>{{search}}</p>
  </div>
</template>

<script>
// import Books from "@/components/Books.vue";
// import OneBook from "@/components/OneBook.vue";

export default {
  name: "searchEngine",
  data() {
    return {
      search: ""
    };
  },
  components: {
    // Books,
    // OneBook
  },
  props: ["value"],
  methods: {
    handleChange(event) {
      console.log(event.target.value);
      this.$emit("value", event.target.value);
    }
  }
  // computed: {
  //   test() {
  //     this.handleChange(this.search);
  //   }
  // }
  // computed: {
  //   searchBar2() {
  //     if (this.search == "") {
  //       return books;
  //     } else {
  //       console.log(this.search);
  //       return books.filter(
  //         x =>
  //           x.title.toUpperCase().includes(this.search.toUpperCase()) ||
  //           x.description.toUpperCase().includes(this.search.toUpperCase())
  //       );
  //     }
  //   }
  // }
};
</script>

<style>
</style>

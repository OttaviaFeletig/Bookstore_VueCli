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
export default {
  name: "searchEngine",
  data() {
    return {
      search: ""
    };
  },
  props: ["value"],
  methods: {
    handleChange(event) {
      console.log(event.target.value);
      this.$emit("value", event.target.value);
    }
  }
};
</script>

<style>
</style>

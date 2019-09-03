<template>
  <div id="carouselExampleControls" class="carousel slide" data-ride="carousel">
    <div class="carousel-inner">
      <div v-for="(book, i) in allBooks" :key="i" v-if="i == index" class="carousel-item active">
        <img :src="book.detalle" class="d-block img_modal" alt="..." />
      </div>

      <div v-else class="carousel-item">
        <img :src="book.detalle" class="d-block img_modal" alt="..." />
      </div>
    </div>

    <a
      class="carousel-control-prev"
      href="#carouselExampleControls"
      role="button"
      data-slide="prev"
    >
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Previous</span>
    </a>
    <a
      class="carousel-control-next"
      href="#carouselExampleControls"
      role="button"
      data-slide="next"
    >
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">Next</span>
    </a>
  </div>
</template>

<script>
export default {
  name: "carousel",
  props: ["img", "allBooks", "index"]
};
</script>

<style>
.img_modal {
  width: 500px;
  margin-left: 275px;
}
</style>

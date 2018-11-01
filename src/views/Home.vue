<template>
  <Books :books="myBooks"/>
</template>

<script>
// @ is an alias to /src
import Books from '@/components/Books.vue'

export default {
  name: 'home',
  data: function() {
      return {
        myBooks: []
      }
    },
  components: {
    Books
  }
}
</script>

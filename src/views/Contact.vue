<template>
        <test :myName="name" :myAge="age" :number="myArray" />
</template>

<script>
// @ is an alias to /src
import test from '@/components/test.vue'

export default {
  name: 'contact',
  components: {
    test
  },
  data(){
    return{
      name: 'Otta',
      age: 24,
      myArray: [1, 2, 3, 4]
    }
  }
}
</script>
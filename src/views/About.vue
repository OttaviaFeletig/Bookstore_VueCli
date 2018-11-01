<template>
    <Test :myName="name" />
</template>

<script>

import Test from '@/components/Test.vue'
export default {
   name: 'about',
   data() {
       return{
           name: 'Ottavia',
           age: 24,
           array: [1, 2, 3, 4],
           numbers: 3
       }
   }
}
</script>

<template>
  <Child />
</template>
<script>
import Child from '~/components/Child'
export default{
  components:{
    Child
  },
  

}

</script>

<style>

</style>


// 부모
// <template>
//   <button @click="message = 'Good?'">
//     click
//   </button>
//   <h1>App: {{ message }}</h1>
//   <Parent :msg="message" />
// </template>

// <script>
// import { computed } from 'vue'
// import Parent from '~/components/Parent'
// export default {
//     components: {
//         Parent
//     },
//     data() {
//         return {
//           message: "Hello World"
//         }
//     },
//     provide(){
//       return{
//         msg: computed(()=> this.message )
//       }
//     },

// }
// </script>

// <style lang="scss" scoped>

// </style>
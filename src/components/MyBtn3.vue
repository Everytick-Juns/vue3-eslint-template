<template>
  <div class="btn">
    <slot></slot>
  </div>
  <h1 @dblclick="$emit('click', $event)">
    ABC
  </h1>
  <input
    type="text"
    v-model="msg" />
</template>
<script>
export default {
    emits: [
      'click',
      'changeMsg'
    ],
    data() {
      return {
        msg: ''
    }
    
  },
  watch: {
      msg() {
        this.$emit('changeMsg', this.msg)
      }
    }
}
</script>

<style scoped lang="scss">
.btn {
    display: inline-block;
    margin: 4px;
    padding: 6px 12px;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;
    &.large {
        font-size: 20px;
        padding: 10px 20px;
    }
}
</style>

// 부모
// <template>
//   <MyBtn
//     @click="log"
//     @change-msg="logMsg">
//     Banana
//   </MyBtn>
// </template>

// <script>
// import MyBtn from '~/components/MyBtn3'
// export default {
//     components: {
//         MyBtn
//     },
//     data() {
//         return {
//         }
//     },
//     methods: {
//       log(e) {
//         console.log('Click')
//         console.log(e)
//       },
//       logMsg(msg){
//         console.log(msg)
//       }

//     },
    


// }
// </script>

// <style lang="scss" scoped>

// </style>
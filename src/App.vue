<template>
  <button @click="add">
    ADD
  </button>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
</template>

<script>
export default{
  data(){
    return {
      // Getter, Setter
      msg: 'Hello Computed!'
    }
  },
  computed:{
    //Getter
    // reversedMessage(){
    //   return this.msg.split('').reverse().join('')
    // }
    reversedMessage: {
      get() {
        return this.msg.split('').reverse().join('')
    },
      set(value) {
        // this.msg = value
        console.log(value)
      }                
    }
  },
  methods: {
    add() {
      this.reversedMessage += '!?'
    }
  }
}
</script>
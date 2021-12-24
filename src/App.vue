<template>
  <h1>{{ count }}</h1>
</template>

<script>
  export default {
    data() {
      return {
        count: 2
      }
    },
    beforeCreate(){// 데이터가 생성되기 전 가장 처음으로 실행됨.
      console.log('beforeCreated!', this.count)
    },
    created(){// 데이터가 생성된 이후, html과 연결되기 전, 활용도 높고 중요
      console.log('Created!', this.count)
    },
    beforeMount(){ // html과 연결 되기 전 - 활용도 떨어짐.
      console.log('beforeCreated!')
      console.log(document.querySelector('h1'))
    },
    mounted(){// html과 연결 된 후 , 활용도 높고 중요
      console.log("Mounted!")
      console.log(document.querySelector('h1'))
    },
  }
</script>
<template>
  <div @click="par1">
    <input
      class="parent"
      type="text"
      @click.stop="child1"
      @keydown.ctrl.enter="handler" />
  </div>
</template>
<script>
export default {
    data() {
        return {

        }
    },
    methods: {
        par1(){
            console.log("parent")
        },
        child1(){
            console.log("child")
        },
        handler() {
                  console.log("Enter!!!!")
            }
        },

    }
</script>

<style lang="scss" scoped>
.parent {
    width: 200px;
    height: 100px;
    background-color: royalblue;
    margin: 10px;
    padding: 10px;
    overflow: auto;
    .child {
        width: 100px;
        height: 200px;
        background-color: orange;
    }
}
</style>
  
<template>
  <Hello ref="hello" />
</template>

<script>
import Hello from '~/components/Hello'
export default {
    components: {
      Hello
    },
    data() {
        return {
            message: "Hello World"
        }
    },
    mounted() {
        console.log(this.$refs.hello.$refs.good)
    }

}
</script>

<style lang="scss" scoped>

</style>
<template>
  <div class="btn">
    <slot></slot>
  </div>
    
  <h1
    v-bind="$attrs"></h1>
</template>
<script>
export default {
    inheritAttrs: false,

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
<template>
  <div
    class="container"
  >
    <slot></slot>
  </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
.container {
  padding-left: 20px;
  padding-right: 20px;
  position: relative;
  @include mq(md) {
    max-width: 672px;
    margin-right: auto;
    margin-left: auto;
  }
  @include mq(xl) {
    max-width: 1052px;
  }
}
</style>

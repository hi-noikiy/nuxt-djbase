/**
* header组件
*/
<template>
  <header class="header" :class="{ 'is-fixed': fixed }">
    <div class="header_left">
      <slot name="left"></slot>
    </div>
    <slot name="title">
      <h1 class="header_title" v-text="title"></h1>
    </slot>
    <div class="header_right">
      <slot name="right"></slot>
    </div>
  </header>
</template>
<script>
  export default {
    name: 'header-fix',
    props: {
      title: String,
      fixed: Boolean
    }
  }
</script>

<style lang="scss" rel="stylesheet/scss">
  @import "~assets/scss/mixin";

  .header {
    @include flex();
    align-items: center;
    @include ht-lineHt(92px);
    background-color: #fff;
    text-align: center;
    font-size: 16px;
    color: #333;
    padding: 0 toRem(20px);

    &.is-fixed {
      position: fixed;
      z-index: 1;
      top: 0;
      left: 0;
      right: 0;
    }

    .header_left {
      flex: 1;
      text-align: left;

      a {
        color: #333;
      }
    }

    .header_title {
      flex: 14;
      @extend %ellipsis;
      color: #333;
      font-size: 16px;
    }

    .header_right {
      flex: 1;
      text-align: right;
      font-size: 14px;
    }

    .webapp-left {
      font-size: 20px;
    }

    .webapp-search {
      font-size: 19px;

      &:before {
        color: #333;
      }
    }

    .webapp-category {
      font-size: 20px;

      &:before {
        color: #333;
      }
    }
  }
</style>

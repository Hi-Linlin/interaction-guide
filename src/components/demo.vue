<template>
  <div class="demo" layout="column top-center">
    <div class="demo__ground" layout="row cenetr-center">
      <slot name="b"></slot>
      <slot name="g"></slot>
    </div>
    <div class="demo__footer" layout="row cenetr-center">
      <div class="demo__attitude">🤔</div>
      <div class="demo__attitude">😘</div>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      align: {
        default: 'h'
      }
    },
    name: 'app'
  };
</script>

<style lang="scss">
  $primary: #f7ff4b;

  .demo {
    background: #f6f6f6;
    padding: 40px 30px 20px;
    margin-bottom: 20px;
    margin-left: -10px;

    &__attitude {
      flex-basis: 50%;
      text-align: center;
      padding: 20px 0 0;
    }

    &__ground {
      > * {
        flex-basis: 50%;
        display: flex;
        justify-content: center;
        align-content: center;
      }
    }
  }
</style>

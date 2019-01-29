<template>
  <div>
    <div class="g-text-box g-colour-border">渐变边框</div>
    <div class="g-text-box g-colour-text">渐变文字</div>
    <div class="g-text-box g-dynamic-border">动态边框</div>
  </div>
</template>

<script>
    export default {
      data () {
        return {
        }
      },
      props: [],
      mounted () {

      },
      activated () {
      },
      deactivated () {
      },
      components: {

      },
      computed: {
      },
      methods: {
      },
      watch: {
      }
    }
</script>

<style scoped lang="scss">
  @import '../assets/css/mixin.scss';

  .g-text-box{
    width: 100px;
    line-height: 30px;
    font-size: 20px;
    color: #333;
    margin: 10px;
    text-align: center;
  }
  .g-colour-border{
    border: .02rem solid transparent;
    background-image: linear-gradient(to left, #fff,#fff), linear-gradient(to left, #1514fb, #e77e0e 95%);
    background-origin: border-box;
    background-clip: content-box, border-box;
    background-size: cover;
  }
  .g-colour-text{
    background-image: linear-gradient(to left, #1b10fb, #e7a711 95%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .g-dynamic-border{
    position: relative;
    --dynamic-width: 100px;
    --dynamic-height: 30px;
    --dynamic-border: 2px;
  }
  .g-dynamic-border::before {
    content: '';
    position: absolute;
    left: 0; top: 0; right: 0; bottom: 0;
    border: var(--dynamic-border) solid #cd0000;
    animation: borderAround 1.5s infinite linear;
  }
  @keyframes borderAround {
    0%, 100% { clip: rect(0 var(--dynamic-width) var(--dynamic-border) 0); }
    25% { clip: rect(0 var(--dynamic-width) var(--dynamic-height) calc(var(--dynamic-width) - var(--dynamic-border))); }
    50% { clip: rect(calc(var(--dynamic-height) - var(--dynamic-border)) var(--dynamic-width) var(--dynamic-height) 0); }
    75% { clip: rect(0 var(--dynamic-border) var(--dynamic-height) 0); }
  }
</style>

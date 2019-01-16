<template>
  <div class="g-3d-rotate">
    <div class="g-quan"></div>
    <div class="g-rotate-quan">
      <div class="g-ball-box">
        <div class="g-blue-ball"></div>
      </div>
    </div>
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

  .g-3d-rotate{
    position: absolute;
    .g-quan{
      position: relative;
      @include wh(476px,210px);
      background: url("../assets/images/quanquan.png") no-repeat;
      background-size: contain;
    }
    .g-rotate-quan{
      position: absolute;
      top: 50%;
      left: 50%;
      @include wh(476px,210px);
      margin-top: -105px;
      margin-left: -238px;
      border-radius: 50%;
      animation: quan 3s 0.5s ease-in-out infinite;
      transform: rotate(-3deg);
      .g-ball-box{
        position: absolute;
        left: 95%;
        top: 0;
        margin-top: -30px;
        margin-left: -10px;
        opacity: 0;
        animation: orbit 3s 0s ease-in-out infinite ,star_ani_00 0.5s 0.5s linear forwards;
        .g-blue-ball{
          @include wh(60px,60px);
          background: linear-gradient(180deg,#00a1ff,#00deff);
          border-radius: 50%;
          animation: invert 3s 0.5s ease-in-out infinite;
        }
      }
      &:last-child{
        animation-delay: 2s;
        .g-ball-box{
          animation: orbit 3s 1.5s ease-in-out infinite ,star_ani_00 0.5s 2s linear forwards;
          .g-blue-ball{
            animation-delay: 2s;
          }
        }
      }
    }
  }
  @keyframes star_ani_00 {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }
  @keyframes quan {
    0% {
      z-index: 20;
    }
    20%{
      z-index: 20;
    }
    21% {
      z-index: 99;
    }
    99.9%{
      z-index: 99;
    }
    100% {
      z-index: 20;
    }
  }
  @keyframes orbit {
    0% {
      transform: translateX(0);
    }
    50%{
      transform: translateX(-480px);
    }
    100% {
      transform: translateX(0);
    }
  }
  @keyframes invert {
    0% {
      transform: translateY(14px) scale(0.4);
    }
    50%{
      transform: translateY(190px) scale(1);
    }
    100% {
      transform: translateY(14px) scale(0.4);
    }
  }
</style>

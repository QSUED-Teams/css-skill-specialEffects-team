<template>
  <div class="g-index-wrap flex-box">
    <div class="line-box">
      <h4>自适应文本框</h4>
      <v-adaptive-textarea class="g_textarea" :minHeight="60" v-model="ceshitextarea"></v-adaptive-textarea>
      <h4>文字边框特效</h4>
      <v-text-effect></v-text-effect>
    </div>
    <div class="line-box"><!--style="margin-bottom: 240px"-->
      <h4>3D旋转球</h4>
      <v-ball-rotate class="g-3d-rotate"></v-ball-rotate>
    </div>
  </div>
</template>

<script>
import {mapState , mapMutations, mapActions} from 'vuex'

export default {
  name: 'App',
  data() {
    return {
      ceshitextarea: '',
    }
  },
  computed: {},
  mounted() {
  },
  components: {
  },
  methods: {
  }
}
</script>

<style scoped lang="scss">
  @import '../assets/css/mixin';
  .g-index-wrap{
    z-index: 2;
    align-items: flex-start;
  }
  h4{
    margin-top: 10px;
    font-size: 20px;
  }
  .g_textarea{
    width: 20%;
    @include sc(20px,#666);
    line-height: 30px;
    margin-left: 10px;
  }
  .g-3d-rotate{
    left: 20px;
  }
  .line-box{
    position: relative;
    width: 50%;
  }
</style>

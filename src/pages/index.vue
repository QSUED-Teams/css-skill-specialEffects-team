<template>
  <div class="g-index-wrap">
    <h4>自适应文本框</h4>
    <v-adaptive-textarea class="g_textarea" :minHeight="60" v-model="ceshitextarea"></v-adaptive-textarea>
    <h4>3D旋转球</h4>
    <v-ball-rotate class="g-3d-rotate"></v-ball-rotate>
    <h4 style="margin-top: 240px">文字边框特效</h4>
    <v-text-effect></v-text-effect>
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
    position: relative;
    z-index: 2;
  }
  h4{
    font-size: 20px;
  }
  .g_textarea{
    margin: 20px;
    width: 10%;
    @include sc(20px,#666);
    line-height: 30px;
  }
  .g-3d-rotate{
    left: 20px;
  }
</style>

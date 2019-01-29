<template>
  <div class="g-table-textarea" :style="{minHeight: minHeight+'px'}">
    <span v-html="spanVal"></span>
    <textarea :value="value" @input="$emit('input', $event.target.value)"></textarea>
  </div>
</template>

<script>
    export default {
      data () {
        return {
          spanVal: '',
        }
      },
      props: ['value','minHeight'],
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
        value: function (val) {
          this.spanVal = val.replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/<=/g,'&le;').replace(/>=/g,'&ge;').replace(/[\r|\n]/g,`</br>`).replace(/\s/g,'&#160;');
        }
      }
    }
</script>

<style scoped lang="scss">
  @import '../assets/css/mixin.scss';

  .g-table-textarea{
    /*利用span内容自动撑起最外部div高度，textarea则高度100%自适应高度*/
    position: relative;
    border: 1px solid;
    min-height: 50px;/*保持最小高度*/
    span{
      word-wrap:break-word;
      word-break: break-all;
      line-height: inherit;
      color: #666;
      display:block;
      font-size: inherit;
    }
    textarea{
      position: absolute;
      top: 0;
      left: 0;
      @include wh(100%,100%);
      font-size: inherit;
      color: inherit;
      line-height: inherit;
      resize:none;
      overflow:hidden;
      word-break: break-all;
    }
  }
</style>

<template>
  <div>
    <h2>页面：</h2>
    <!-- 尺寸-->
    <section>
      <h4>设计尺寸</h4>
      <ul>
        <li>
          <h5>WIN: 1366 * 768</h5>
        </li>
        <li>
          <h5>MAC: 1280 * 800</h5>
        </li>
        <li>
          <h5>浏览器顶栏高度:  200px以内，以chrome为准</h5>
        </li>
        <li>
          <h5>在设计纵向不滚动的页面时，高度应该减去顶栏高度</h5>
        </li>
      </ul>
    </section>
    <!-- 字号-->
    <section>
      <h4>字号（最少区分三种类型）</h4>
      <ul>
        <li>
          <h5>标题:   16 - 24px，无硬性规定</h5>
        </li>
        <li>
          <h5>内容正文:   14px</h5>
        </li>
        <li>
          <h5>辅助文字:   说明，提醒等类型，12px字号。颜色 < 50%灰度。</h5>
        </li>
      </ul>
    </section>
    <!-- 图片-->
    <section>
      <h4>图片</h4>
      <ul>
        <li>
          <h5>至少1px的边框，防止图片与页面背景重合</h5>
        </li>
        <li>
          <h5>加载不出图片时，应有默认背景</h5>
        </li>
      </ul>
    </section>
    <!-- 页面跳转-->
    <section>
      <h4>页面跳转</h4>
      <ul>
        <li>
          <h5>有入口就得有出口，别让用户去习惯浏览器自带的返回</h5>
        </li>
        <li>
          <h5>如果是针对于某个对象进行的操作，内容又不多时，可以用弹框取代页面跳转。弹框能更清晰的了解页面层级关系</h5>
        </li>
      </ul>
    </section>
    <!-- 表格-->
    <section>
      <h4>表格</h4>
      <ul>
        <li>
          <h5>表头:   样式上应有明显差别。  字号、颜色、加粗等</h5>
        </li>
        <li>
          <h5>单元格:   文字左对齐，数字金额等右对齐</h5>
        </li>
        <li>
          <h5>统一操作按钮样式，常见操作可用icon代替，不易识别的icon最好用文字代替</h5>
        </li>
        <li>
          <h5>内容换行:   表格换行总会很难看，如果要换行，就把内容显示完整，不要超过第二行又给省略了</h5>
        </li>
        <li>
          <h5>内容换行:   表格换行总会很难看，如果要换行，就把内容显示完整，不要超过第二行又给省略了</h5>
        </li>
        <li>
          <h5>内容不换行:   超出一行省略，鼠标hover展示完整内容</h5>
        </li>
        <li>
          <h5>内容超过20-30行，增加分页</h5>
        </li>
        <li>
          <h5>增大每行行高可以减少视觉压力与错行率。如果行高固定很小，可用斑马纹类型表格（基偶行的背景色不一样）</h5>
        </li>
        <li>
          <h5>表格列数太多导致横向滚动时，操作列可单独提出固定</h5>
        </li>
        <li>
          <h5>表格列数太多导致横向滚动时，操作列可单独提出固定</h5>
        </li>
      </ul>
    </section>
    <!-- 分页-->
    <section>
      <h4>分页</h4>
      <ul>
        <li>
          <h5>表头:   样式上应有明显差别。  字号、颜色、加粗等</h5>
        </li>
        <!-- TODO:填完内容-->
      </ul>
    </section>
  </div>
</template>

<script>
  import demo from './demo.vue';

  export default {
    props: {
      align: {
        default: 'h'
      }
    },
    name: 'app',
    components: {
      demo
    }
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

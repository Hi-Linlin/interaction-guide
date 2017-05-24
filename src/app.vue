<template>
  <div class="app">
    <section>
      <h1>WebAPP 基本交互指南</h1>
      <p>@eleme</p>
    </section>

    <h2>你必须做的：</h2>
    <!-- 不要-->
    <section>
      <h4>不要</h4>
      <ul>
        <li>
          <h5>不要用window.alert</h5>
        </li>
        <li>
          <h5>不要让favicon为空</h5>
        </li>
      </ul>
    </section>
    <!-- 他在哪里-->
    <section>
      <h4>告诉用户，他在哪里、这是什么</h4>
      <ul>
        <li>
          <h5>导航栏随时可见， 菜单TAB有清晰可见的active状态来指引当前用户所在位置</h5>
        </li>
        <li>
          <h5>按钮、链接、菜单、文本的样式自然应该有比较大的区别</h5>
          <demo>
            <div slot="b">
              <a href="#">按钮</a>
              <span> 链接 </span>
              <span>文字</span>
            </div>
            <div slot="g">
              <div class="button" data-content="这是按钮"></div>
              <a href="#"> 链接 </a>
              <span> 文字 </span>
            </div>
          </demo>
        </li>
        <li>
          <h5>输入框要有placeholder提示</h5>
          <demo>
            <div slot="b">
              <input type="text">
            </div>
            <div slot="g">
              <input type="text" placeholder="告诉我你的银行密码">
            </div>
          </demo>
        </li>
        <li>
          <h5>使用图标按钮要有意义贴切基本认知还要给予tooltip提示（以添加用户为例）</h5>
          <demo>
            <div slot="b">
              <div class="icon-button">
                <i class="icon">&#xe668;</i>
              </div>
            </div>
            <div slot="g">
              <div class="icon-button tooltip" data-tooltip="新建用户">
                <i class="icon">&#xe61f;</i>
              </div>
            </div>
          </demo>
        </li>
      </ul>
    </section>
    <!-- 操作反馈-->
    <section>
      <h4>告诉用户，他现在做了什么（操作输入反馈）</h4>
      <ul>
        <li>
          <h5>按钮及链接等可点击物体必须有<code>hover</code>及<code>press</code>和<code>disabled</code>状态</h5>
          <demo>
            <div slot="b">
              <div class="button" data-content="这是按钮？">
              </div>
              <div class="button" data-content="disabled">
              </div>
            </div>
            <div slot="g">
              <div class="button effect" data-content="这是按钮" data-hover="我被hover了" data-active="我被press了">
              </div>
              <div class="button disabled" data-content="disabled">
              </div>
            </div>
          </demo>
        </li>
        <li>
          <h5>同样的，输入框等表单组件必须有<code>hover</code>和<code>focus</code>和<code>disabled</code>的状态</h5>
          <demo>
            <div slot="b">
              <input type="text" placeholder="请输入xx"/>
              <input type="text" placeholder="disabled" readonly/>
            </div>
            <div slot="g">
              <input type="text" class="effect" placeholder="请输入xx"/>
              <input type="text" class="disabled" placeholder="disabled" readonly/>
            </div>
          </demo>
        </li>
      </ul>
    </section>
    <!-- 状态反馈-->
    <section>
      <h4>告诉用户，正在发生什么（进行中状态反馈）</h4>
      <ul>
        <li>
          <h5>点击按钮提交表单时给一个<code>loading</code>指示（按钮局部，窗口全局选择看具体情况），并且disable相关行动操作防止重复提交</h5>
          <demo>
            <div slot="b">
              <div class="form-button" data-content="点击提交">
              </div>
            </div>
            <div slot="g">
              <div @click="buttonLoading = !buttonLoading" class="form-button" :class="{'loading': buttonLoading}" data-content="点击提交">
                <span class="spinner earth"></span>
              </div>
            </div>
          </demo>
        </li>
        <li>
          <h5>同样的，加载列表或图表数据时给予区域一个<code>loading</code>指示</h5>
          <demo>
            <div slot="b">
              <div class="list" :class="{'loading': listLoading}">
                <div class="units"></div>
              </div>
            </div>
            <div slot="g">
              <div class="list" :class="{'loading': listLoading}">
                <div class="units"></div>
                <span class="spinner earth"></span>
              </div>

            </div>
          </demo>
        </li>
      </ul>
    </section>

    <spec></spec>

  </div>
</template>

<script>
  import demo from './components/demo.vue';
  import spec from './components/spec.vue';

  export default {
    name: 'app',
    components: {
      demo,
      spec
    },
    data() {
      return {
        buttonLoading: false,
        listLoading: false
      };
    },
    mounted() {
      setTimeout(() => {
        this.listLoading = true;
      }, 1000);
    },
    watch: {
      listLoading(val) {
        if (val) {
          setTimeout(() => {
            this.listLoading = false;
          }, 3000);
        } else {
          setTimeout(() => {
            this.listLoading = true;
          }, 2000);
        }
      }
    }
  };
</script>

<style lang="scss">
  @import "./scss/index";
</style>

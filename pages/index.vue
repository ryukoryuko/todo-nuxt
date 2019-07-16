<template>
  <div id="main" class="main">
    <section><!--ここにコンポーネントを追加していく-->
      <h2><a href="/">ToDoList</a></h2>
      <Form /><!--ToDoの入力フォーム-->
      <AllFinishClear /><!--全て終了・終了タスクをクリア-->
      <TodoOutput /><!--入力したタスクを表示-->
      <DisplayTM /><!--終了した・してない・すべてのタスクなど、表示を管理-->
    </section>
  </div>
</template>

<script>
import Form from '~/components/Form.vue'
import AllFinishClear from '~/components/AllFinishClear.vue'
import TodoOutput from '~/components/TodoOutput.vue'
import DisplayTM from '~/components/DisplayTM.vue'
import Vue from 'vue'  //下の共通インスタンスを使うのに必要なので読み込んでおく
Vue.prototype.$EventBus = new Vue()//どこのコンポーネントからもアクセスできるプロトタイプ宣言。イベント使用時に一時的にパスを預けてイベントをパスを渡す。

export default {
  components: {
    Form,AllFinishClear,TodoOutput,DisplayTM
  }
}
</script>

<style>
.parent{
  height:auto;
  width:100%;
  position: relative;
}
.main{
  width:95%;
  margin: 0 auto;
  position:absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
}

@media (min-width: 768px) {
  h2 {
  position: relative;
  text-align: center;
  padding-bottom:10px;
  color:#8258FA;
  font-size: 60px;
  }
}

h2 {
  position: relative;
  text-align: center;
  padding-bottom:10px;
  color:#8258FA;
  font-size: 40px;
}

h2:after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 7px;
  background: -webkit-repeating-linear-gradient(-45deg, #6ad1c8, #6ad1c8 2px, #fff 2px, #fff 4px);
  background: repeating-linear-gradient(-45deg, #6ad1c8, #6ad1c8 2px, #fff 2px, #fff 4px);
}
</style>

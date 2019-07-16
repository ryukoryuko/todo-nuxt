<template>
    <div>
        <input type="text" class="input-form" v-model="newItem" placeholder="ここにTODOを記述" @keyup.enter="addItem">
    </div>
</template>


<script>

export default {
  props:{
      type:Object
  },
  data: function(){
      return{
          newItem:'',
      }
  },
  methods:{
    addItem:function(){
        let todo ={
            item:this.newItem
        };
        this.formTodos=[];
        this.formTodos.push(todo);
        this.$EventBus.$emit('bus-event',this.formTodos);//$emitでイベント名と一緒に第二引数で送りたい値を送信
        this.newItem='';//送った後に残った入力フォームを消す
        }
  },
}
</script>


<style>
    .input-form{
        margin-right:10px;
        margin-left:10px;
        margin-top:20px;
        margin-bottom:20px;
        width:95%;
        height:40px;
        font-size:21px;
        border-radius:5px;
    }
    @media (min-width: 768px) {
        .input-form{
            height:65px;
            font-size:30px;
        }
    }
    @media (max-width: 767px) {
        .input-form{
            height:55px;
            font-size:27px;
        }
    }
</style>



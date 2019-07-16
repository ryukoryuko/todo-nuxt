<template>
    <div class="output">
        <ul>
            <li v-for="fff in todoList"><input type="checkbox" @bus-event="ChangeMethod" >{{fff[0].item}}</li>
        </ul>
    </div>
</template>

<script>
import Form from '~/components/Form.vue'

export default {
    components:{
        Form
    },
    data:function(){
        return{
            formTodos:''//Formに渡す用
            ,todoList:[]//ここで値を描画する用。
        }
    },
    mounted: function(){
        this.$EventBus.$on('bus-event', this.ChangeMethod)
    },
    methods:{
        ChangeMethod:function(formTodos){
            this.todoList.push(formTodos)//配列を結合
        }
    }
}
</script>

<style>
    .output{
        margin-top:100px;
        width:100%;
        height:auto;
        font-size:25px;
        border-top:solid 2px #8258FA;
        padding-top:20px;
        max-width:100%;
        min-height:200px;
    }
    input[type=checkbox] {
    width:18px;
    height:18px;
    }

    ul{
        width:100%;
        padding-left:1px;
    }

    li{
        list-style: none;
        margin-bottom:10px;
        width:100%;
    }
    @media (min-width: 768px) {
       .output{
            margin-top:70px;
            width:100%;
            height:auto;
            font-size:30px;
            border-top:solid 2px #8258FA;
            padding-top:20px;
            max-width:100%;
        }
        input[type=checkbox] {
            width:35px;
            height:35px;
        } 
    }
    @media (max-width: 767px) {
       .output{
            margin-top:50px;
            width:100%;
            height:auto;
            font-size:22px;
            border-top:solid 2px #8258FA;
            padding-top:20px;
            max-width:100%;
        }
        input[type=checkbox] {
            width:23px;
            height:23px;
        } 
    }
</style>




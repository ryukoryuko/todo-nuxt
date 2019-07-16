<template>
    <div>
        <input type="button" value="Completed All Task" class="btn-custom-L" @click="CompletedAllTask"><!--ボタン押下で全部のtodoをこなした扱いにするボタン -->
        <input type="button" value="Clear Completed" class="btn-custom-R" @click="ClearCompleted"><!--ボタン押下でこなした扱いtodoをすべて消すボタン --> 
    </div>
</template>

<!--todoを全部済に変えるのがコンプリーテッドオールタスク-->

<!--済のtodoを削除するのがクリアコンプリーテッド-->
<script>
export default {
    methods:{
        CompletedAllTask(){ 
            let chk = document.getElementsByTagName('input');
            for (let i = 0; i < chk.length; i++) {
                if (chk[i].type=='checkbox'){
                    chk[i].checked='checked';
                }
            }
        },
        ClearCompleted(){
           let chkli = document.getElementsByTagName('li');
           let chkdel = document.getElementsByTagName('input');
            for (let i = 0; i < chkdel.length; i++) {
                if (chkdel[i].type=='checkbox'&& chkdel[i].checked==true){
                    i=i-3;
                    chkli[i].remove();
                    i=i+2;
                }
            }
        }
    }
}
</script>


<style>
    .btn-custom-R{
        float:right;
        padding: 0.5em 1.5em;
        text-decoration: none;
        color:black;
        border: solid 2px #67c5ff;
        border-radius: 3px;
        transition: .4s;
        font-weight:bold;
    }
    .btn-custom-R:hover {
        background: #67c5ff;
        color: white;
    }
    
    .btn-custom-L{
        float:left;
        padding: 0.5em 1.5em;
        text-decoration: none;
        color:black;
        border: solid 2px #67c5ff;
        border-radius: 3px;
        transition: .4s;
        font-weight:bold;
    }
    .btn-custom-L:hover {
        background: #67c5ff;
        color: white;
    }
    .max{
        max-width:100%;
    }
    
    @media (max-width: 767px) {
        .btn-custom-L{
            padding: 0.5em 0.6em;
            font-size:15px;
        }
        .btn-custom-R{
            float:right;
            padding: 0.5em 0.6em;
            font-size:15px;

        }
    }
    @media (min-width: 768px) {
        .btn-custom-L{
        padding: 0.5em 1em;
        font-size:23px;
        margin-left:15px;
        }
        .btn-custom-R{
        padding: 0.5em 1em;
        font-size:23px;
        margin-right:15px;
        }
    }        
</style>


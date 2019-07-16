<template>
    <div class="display-tm">
        <input type="button" value="All" class="bottom-btn" @click="all"><!-- 済か否かにかかわらずすべてのtodoを表示--> 
        <input type="button" value="Uncomplate" class="bottom-btn" @click="uncomplate"> <!--済じゃないtodoだけを表示-->
        <input type="button" value="Complated" class="bottom-btn" @click="complated"> <!--済のtodoだけを表示する-->
    </div>
</template>

<!-- allはinputを取得後にチェックボックスであるかを判定、チェックボックスなら表示する
uncomplateは、inputを取得後にチェックボックスであるかを判定、trueなら非表示、falceなら表示
complatedは、inputを取得後にチェックボックスであるかを判定、trueなら表示、falceなら非表示-->
<script>
export default {
    methods:{
        uncomplate(){
            let lichk = document.getElementsByTagName('li');
            let disp = document.getElementsByTagName('input');
            for (let i = 0; i < disp.length; i++) {
                if (disp[i].type=='checkbox' && disp[i].checked==true){
                   lichk[i-3].style.display="none";
                }else if(disp[i].type=='checkbox' && disp[i].checked==false){
                    lichk[i-3].style.display="block";
                }
            }
        },
        complated(){
            let lichk = document.getElementsByTagName('li');
            let disp = document.getElementsByTagName('input');
            for (let i = 0; i < disp.length; i++) {
                if (disp[i].type=='checkbox' && disp[i].checked==true){
                    lichk[i-3].style.display="block";
                }else if(disp[i].type=='checkbox' && disp[i].checked==false){
                    lichk[i-3].style.display="none";
                }

            }
        },
        all(){
            let lichk = document.getElementsByTagName('li');
            let disp = document.getElementsByTagName('input');
            for (let i = 0; i < disp.length; i++) {
                if (disp[i].type=='checkbox'){
                    lichk[i-3].style.display="block";
                }
            }
        }
    }
}
</script>


<style>
    .display-tm{
        position: relative;
        border-top:solid 2px #8258FA;
        padding-top:20px;
        max-width:100%;
        height:100px;
    }

    .bottom-btn{
        float:right;
        padding: 0.5em 1.5em;
        margin-left:15px;
        text-decoration: none;
        color:black;
        border: solid 2px #67c5ff;
        border-radius: 3px;
        transition: .4s;
        font-size:12px;
        font-weight:bold;
    }
    .bottom-btn:hover {
        background: #67c5ff;
        color: white;
    }
    @media (min-width: 768px) {
        .bottom-btn{
            margin-left:15px;
            font-size:23px;
            margin-right:15px;
        }
    }
    @media (max-width: 767px) {
        .bottom-btn{
        padding: 0.3em 1em;
        margin-left:5px;
        font-size:15px;
        }
    }
</style>

<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对vue的评论</h1>
          </div>
        </div>
      </div>
    </header>

    <div class="container">
     <Add :addComment="addComment"/>,
     <List :comments="comments" :delComment="delComment"/>
     </div>
    </div>
 
</template>
<script>
import Add from './components/Add.vue'
import List from './components/List.vue'
export default{
       data(){
         return{
           comments:[//数据在那个组件，更新数据的行为(方法)就应该定义在那个组件
             {name:"BOB",content:"vue还不错"},
             {name:"JACK",content:"有点难"},
             {name:"Marry",content:"so easy"},
           ]
         }
       },
         methods:{
      //添加评论     
      addComment(comment){
        this.comments.unshift(comment)
      },
      delComment(index){
        this.comments.splice(index,1)
      }
    },
    components:{
        Add,
        List
    },
  
}
</script>

<style>

</style>
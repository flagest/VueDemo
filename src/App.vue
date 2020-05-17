<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对Vue的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <!--将信息传递给子组件-->
      <Add :addComment="addComment"/>
      <!--组件之间的通信，最原始的方式是通过标签-->
      <List :comments="comments"/>
    </div>
  </div>
</template>


<script>
  import Add from './components/Add.vue'
  import List from './components/List.vue'

  export default {
    data() {
      return {
        comments: [  //数据在哪一个组件，更新数据的行为（方法）就应该定义在哪一个组件
          {
            name: "Bob",
            content: "Vue so easy"
          },
          {
            name: "zhangsan",
            content: "Vue so zhangsan"
          },
          {
            name: "lisi",
            content: "Vue so lisi"
          }
        ]
      }
    },
    methods: {
      //添加评论
      addComment(comment) {
        //将每一个评论添加到数组的最前面（unshift，就是代表最前面）
        this.comments.unshift(comment)

      }
    },
    components: {
      Add,
      List
    }
  }

</script>
<style>

</style>

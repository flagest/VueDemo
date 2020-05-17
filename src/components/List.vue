<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <!--这里使用的技术hrm（热模替换，没有刷新页面）-->
    <h2 v-show="comments.length===0">暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <Item v-for="(comment, index) in comments" :key="index" :comment="comment"
            :deleteComment="deleteComment" :index="index"/>

    </ul>
  </div>
</template>
<script>
  import Item from './Item.vue'

  export default {
    //接受父组件传递过来的值,这个属性就会成为组件对象的属性
    props: ['comments', 'deleteComment'],
    components: {
      Item
    }
  }

</script>
<style>
  .reply {
    margin-top: 0px;
  }

</style>

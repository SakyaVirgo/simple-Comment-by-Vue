<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 style='display: none'>暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <li class="list-group-item" v-for="(comment, index) in comments" track-by="id">
            <item :comment="comment" :key="index" :index="index"
              :delete-comment="deleteComment"></item>
      </li>
    </ul>
  </div>
</template>

<script>
  import item from './commentItem.vue'
  export default {
    props: [
        'comments',
        'deleteComment'

    ],
    components: {
        item
    }
  }
</script>

<style scoped>
  .reply {
    margin-top: 0px;
  }
</style>

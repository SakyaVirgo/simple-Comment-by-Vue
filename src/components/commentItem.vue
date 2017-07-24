<template>
  <div>
    <div class="handle">
      <a href="javascript:;" @click="removeComment">删除</a>
    </div>
    <p class="user"><span >{{comment.username}}</span><span>说:</span></p>
    <p class="centence">{{comment.content}}!</p>
  </div>
</template>

<script>
  export default {
    props: {
        index: Number,
        comment: Object,
        deleteComment: Function

    },
    methods: {
      removeComment () {
          const {username} = this.comment
          if (confirm(`确定要删除${username}的评论么？`)) {
              this.deleteComment(this.index)
          }
      }
    }
  }
</script>

<style scoped>
  li{
    transition: .5s;
    overflow: hidden;
  }
  .handle{
    width: 40px;
    border: 1px solid #ccc;
    background: #fff;
    position: absolute;
    right: 10px;
    top: 1px;
    text-align: center;
  }
  .handle a{
    display: block;
    text-decoration: none;
  }
  .list-group-item .centence {
    padding: 0px 50px;
  }
  .user{
    font-size: 22px;
  }
</style>

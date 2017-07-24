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
        <add :add-comment="addComment"/>
        <list :comments="comments" :delete-comment="deleteComment"/>
      </div>
  </div>
</template>

<script>
  import add from './commentAdd.vue'
  import list from './commentList.vue'
  export default {
      data () {
          return {
              comments: []
          }
      },
      components: {
          add,
          list
      },
    methods: {
          addComment (comment) {
              this.comments.unshift(comment)
          },
          deleteComment (index) {
              this.comments.splice(index, 1)
          }
    },
    // 模拟Ajax发送请求
    created () {
          setTimeout(() => {
             const comments = [
                 {
               username: 'Avril',
               content: 'Vue is not very easy'
             },
             {
                 username: 'Scarlett ',
                 content: 'not interesting'
             }
             ]
            this.comments = comments
          }, 1000)
    }
 }
</script>

<style scoped>
</style>

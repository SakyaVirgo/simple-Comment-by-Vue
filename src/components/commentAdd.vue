<template>
  <div class="col-md-4">
    <form class="form-horizontal">
      <div class="form-group">
        <label>用户名</label>
        <input type="text" class="form-control" placeholder="用户名" v-model="username">
      </div>
      <div class="form-group">
        <label>评论内容</label>
        <textarea class="form-control" rows="6" placeholder="评论内容" v-model="content"></textarea>
      </div>
      <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
          <button type="button" class="btn btn-default pull-right" @click="submit">提交</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
      props: {
        addComment: {
            type: Function,
            required: true
        }
      },
    data () {
      return {
          username: '',
          content: ''
      }
    },
    methods: {
          submit () {
              const {username, content} = this
            // 检查用户输入
              if(!username.trim() || !content.trim()) {
                  alert('please check your WHRITE')
                return
              }

            // 输入内容生成新的对象comment
              const comment = {username, content}
            // 调用添加函数
              this.addComment(comment)
            // 重置清空输入框
            this.username = ''
            this.content = ''
          }

    }
  }
</script>

<style scoped>
</style>

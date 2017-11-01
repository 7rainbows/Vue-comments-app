<template>
  <div class="col-md-4">
    <form class="form-horizontal">
      <div class="form-group">
        <label>用户名</label>
        <input type="text" class="form-control" placeholder="用户名" v-model="userName">
      </div>
      <div class="form-group">
        <label>评论内容</label>
        <textarea class="form-control" rows="6" placeholder="评论内容" v-model="content"></textarea>
      </div>
      <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
          <button type="submit" class="btn btn-default pull-right" @click.prevent="addItem">提交</button>
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
        isRequire: true
      }
    },
    data () {
      return {
        userName: '',
        content: ''
      }
    },
    methods: {
      addItem () {
        let userName = this.userName.trim()
        let content = this.content.trim()
        if (!userName || !content) {
          alert('请输入用户名或内容')
          return
        }
        let comment = {
          userName,
          content
        }
        this.addComment(comment)
        this.userName = ''
        this.content = ''
      }
    }
  }
</script>

<style>

</style>

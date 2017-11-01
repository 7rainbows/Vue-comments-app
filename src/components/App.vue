<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对Vue.js的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <Add :addComment="addComment"/>
      <List :comments="comments" :removeComment="removeComment"/>
    </div>
  </div>
</template>

<script>
  import Add from './Add.vue'
  import List from './List.vue'
  export default {
    data () {
      return {
        comments: [
          {userName: '尤雨溪', content: '不吹不黑,我Vue最牛逼!!'},
          {userName: '大漠穷秋', content: '垃圾渣渣，抄袭我Angular,菜机！！'}
        ]
      }
    },
    components: {
      Add,
      List
    },
    methods: {
      addComment (comment) {
        this.comments.unshift(comment)
      },
      removeComment (index) {
        this.comments.splice(index, 1)
      }
    }
  }
</script>

<style>

</style>

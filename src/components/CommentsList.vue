<template>
  <section class="section">
    <div class="container">
      <div class="block" :key="comment.id" v-for="(comment, index) in comments">
          <Comment :comment="comment" @delComment="delComment(index)"/>
      </div>
    </div>
  </section>
</template>
<script>
import Comment from './Comment'
export default {
    props: {
        comments: Array
    },
    methods: {
        delComment(id) {
        this.comments.splice(id, 1);
        }
    },
    components: {
        Comment
    }
}
</script>

<style scoped>

</style>
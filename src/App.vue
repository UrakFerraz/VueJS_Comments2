<template>
  <section class="hero is-primary">
    <div class="hero-body">
      <p class="title">
        Comentários
      </p>
      <p class="subtitle">
        Teste vue-cli VueJS
      </p>
    </div>
  </section>
  <CommentsInput :comments="this.comments"/>
  <CommentsList :comments="this.comments"/>
</template>

<script>
import './assets/bulma.min.css'
import CommentsInput from './components/CommentsInput'
import CommentsList from './components/CommentsList'

export default {
  name: 'App',
  components: {
    CommentsInput,
    CommentsList
  },
  data() {
    return {
      comments: []
    }
  }
}
</script>

<style>
.block:not(:last-child) {
  margin-bottom: 1.5rem;
}
</style>
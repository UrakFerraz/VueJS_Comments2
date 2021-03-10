<template>
    <div class="box" v-bind:class="{ active: comment.reminder}">
        <button class="delete" @click="$emit('delComment', comment.id)"></button>
        <p>Nome: <strong> {{ comment.nome }} </strong></p>
        <p><strong>Comentário:</strong> {{ comment.mensagem }} </p>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                id: '',
                nome: '',
                mensagem: '',
                reminder: false,
            }
        },
        props: {
            comment: Object
        }
    }
</script>

<style scoped>
.box {
  background-color: #f8ffff;
  position: relative;
}

.box.active::before {
  content: "";
  position: absolute;
  width: 3px;
  height: 60%;
  max-height: 150px;
  left: 0;
  top: 18px;
  background-color: rgb(0, 123, 128);
}

.box .delete {
  position: absolute;
  right: -4px;
  top: -4%;
}
</style>
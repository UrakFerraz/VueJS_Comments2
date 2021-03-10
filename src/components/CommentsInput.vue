<template>
  <section class="section">
    <div class="container">
      <div class="field">
        <label class="label">Nome</label>
        <div class="control">
          <input class="input" type="text" v-model="nome">
        </div>
      </div>
      <div class="field">
        <label class="label">Mensagem</label>
        <div class="control">
          <textarea class="textarea" v-model="mensagem"></textarea>
        </div>
      </div>
    <div class="field">
        <div class="control">
            <label class="checkbox">
            <input type="checkbox" v-model="reminder">
            Marcar como importante
            </label>
        </div>
    </div>
      <div class="field is-grouped">
        <div class="control">
          <button class="button is-link" @click='enviar'>Enviar</button>
        </div>
        <div class="control">
          <button class="button is-link is-light">Apagar</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
    export default {
        props: {
            comments: Array
        },
        data() {
            return {
                id: this.comments.length + 1,
                nome: '',
                mensagem: '',
                reminder: false
            }
        },
        methods: {
            enviar() {
                const name = this.nome == '' ? 'Anônimo' : this.nome
                this.comments.push({
                    id: this.id,
                    nome: name,
                    mensagem: this.mensagem,
                    reminder: this.reminder
                })
            },
        }
    }
</script>

<style scoped>

</style>
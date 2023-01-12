<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="formulário para a criação de ua nova tarefa">
        <input type="text" class="input" placeholder="qual tarefa você deseja?" v-model="descricao">
      </div>

      <div class="column">
        <Temporizador @temporizadorFinalizado="finalizarTarefa"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import {defineComponent} from "vue";
import Temporizador from "@/components/Temporizador.vue";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Formulario",
  emits: ['salvarTarefas'],
  components: {
    Temporizador
  },
  data () {
    return {
      descricao: ''
    }
  },
  methods: {
    finalizarTarefa (tempoDecorrido:number) : void {
      console.log('tempo da tarefa', tempoDecorrido)
      console.log('descrição da tarefa', this.descricao)
      this.$emit('salvarTarefas', {
        duracaoEmSegundos: tempoDecorrido,
        descricao: this.descricao
      })
      this.descricao = ''
    }
  }
}
</script>

<style scoped>

</style>
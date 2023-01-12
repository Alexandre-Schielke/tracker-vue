<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>

    <div class="column is-three-quarter">
      <Formulario @salvarTarefas="salvarTarefa"/>
      <div class="lista">
        <Tarefa v-for="(tarefas, index) in tarefas"  :key="index"/>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from "@/components/BarraLateral.vue";
import Formulario from "@/components/Formulario.vue";
import Tarefa from "@/components/Tarefa.vue";
import ITarefas from "@/interfaces/ITarefas";

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    Formulario,
    Tarefa
  },
  data () {
    return {
      tarefas: [] as ITarefas[]
    }
  },
  methods: {
    salvarTarefas (tarefa: ITarefas) {
      this.tarefas.push(tarefa)
    }
  }
});
</script>

<style>
.lista {
  padding: 15px;
}
</style>

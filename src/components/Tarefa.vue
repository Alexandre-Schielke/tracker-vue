<template>
  <div class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is-7">
        Descrição da tarefa
      </div>
      <div class="column">
        <Cronometro tempoEmsegundos="15"/>
      </div>
    </div>
  </div>
</template>

<script>
import Cronometro from "@/components/Cronometro.vue";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Tarefa",
  components: {
    Cronometro
  }
}
</script>

<style scoped>
.box {
  background-color: #FAF0CA;
}
</style>
<script lang="ts">
import { defineComponent } from "vue";
import BarraLateral from "./components/BarraLateral.vue";

export default defineComponent({
  name: "App",
  components: {
    BarraLateral,
  },
  data () {
    return {
      modoEscuro: false
    }
  },
  methods: {
    alterarModo (modoEscuro: boolean) : void {
      this.modoEscuro = modoEscuro
    }
  }
});
  
</script>

<template>
  <main class="columns is-gapless is-multiline" :class="{ 'modo-escuro' : modoEscuro}">
    <div class="column is-one-quarter">
      <BarraLateral @aoAlterarModo="alterarModo"/>
    </div>
    <div class="column is-three-quarters conteudo">
      <router-view></router-view>
    </div>
  </main>
</template>

<style>
  main{
    --bg-primario: #e1e0dc;
    --bg-barra:#ffffff;
    --texto-primario: #ddd;
    --bg-secundario: #7B2383;
    --bg-box: #3186CD;
    --color-box:#e1e0dc;
  }
  main.modo-escuro{
    --bg-primario:#2b2d42;
    --bg-secundario:#2b2d42;
    --bg-barra: #7B2383;
    --bg-box:#3186CD;
    
  }
  .conteudo{
    background-color: var(--bg-primario);
    color: var(--texto-primario);
  }
  .lista{
    padding: 1.25rem;
  }
</style>

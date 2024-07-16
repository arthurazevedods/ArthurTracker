<script lang="ts">
    import { defineComponent} from 'vue'

    export default defineComponent({
        name: 'BarraLateral',
        emits: ['aoTemaAlterado'],
        data(){
          return {
            modoEscuroAtivo: false
          }
        },
        computed: {
          textoBotao (){
            if(this.modoEscuroAtivo){
              return 'Ativar Modo Claro'
            }else{
              return 'Ativar Modo Escuro'
            }
          }
        },
        methods: {
          alterarTema (){
            this.modoEscuroAtivo = !this.modoEscuroAtivo;
            this.$emit('aoTemaAlterado',this.modoEscuroAtivo);
          }
        }
    })
</script>

<template>
    <header>
        <h1>
            <img src="../assets/Logo.png" alt="Logo da Alura Tracker">
        </h1>
        <button class="button" @click="alterarTema">
          {{ textoBotao }}
        </button>
    </header>
</template>

<style scoped>
  header {
    padding: 1rem;
    background: var(--bg-barra);
    width: 100%;
    height: 100vh;
  }
  header.modo-escuro{
    background-color: var(--bg-barra);
  }
  img{
    border-radius: 8px;
  }
  @media only screen and (max-width: 768px) {
    header {
      padding: 2.5rem;
      height: auto;
    }
  }
</style>
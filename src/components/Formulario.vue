<script lang='ts'>
import { defineComponent } from 'vue';
import Temporizador from './Temporizador.vue';


export default defineComponent({
    name: 'Formulario',
    emits:['aoSalvarTarefa'],
    components:{
        Temporizador
    },
    data() {
        return{
            descricao:''
        }
    },
    methods:{
        finalizarTarefa (tempoDecorrido: number) : void{
            this.$emit('aoSalvarTarefa',{
                duracaoEmSegundos: tempoDecorrido,
                descricao: this.descricao
            })
        },

    }
})
</script>

<template>
    <div class="box formulario">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa deseja iniciar?" v-model="descricao"/>
            </div>
            <div class="column">
                <Temporizador @aoTemporizadorFinalizado="finalizarTarefa"/>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .formulario{
        color: var(--texto-primario);
        background-color: var(--bg-secundario);
        border-radius: 0 0 10px 10px;
    }
    .formulario.modo-escuro{
        color: var(--texto-primario);
        background-color: var(--bg-secundario);
    }
    .input{
        background-color: #ffffff;
        color:black
    }
    .input::placeholder{
        color: black;
    }
</style>
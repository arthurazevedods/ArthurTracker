<script lang="ts">
    import { defineComponent, type PropType } from 'vue';
    import Cronometro from './Cronometro.vue';
    import type ITarefa from '@/interfaces/ITarefa';

    export default defineComponent ({
        name: 'Tarefa',
        components:{
            Cronometro
        },
        props:{
            tarefa: {
                type: Object as PropType<ITarefa>,
                required:true
            }
        }
    });
</script>

<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                {{ tarefa.descricao || "Tarefa sem descrição"}}
            </div>
            <div class="column">
                <Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
            </div>
        </div>
    </div>

</template>

<style scoped>
    .box{
        background-color: #7B2383;
    }
    .column{
        color: #ffffff;
    }
</style>

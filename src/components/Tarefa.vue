<script lang="ts">
    import { defineComponent, type PropType } from 'vue';
    import Cronometro from './Cronometro.vue';
    import type ITarefa from '@/interfaces/ITarefa';
    import Box from './Box.vue';

    export default defineComponent ({
        name: 'Tarefa',
        components:{
            Cronometro, Box
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
    <Box>
        <div class="columns">
            <div class="column is-7">
                {{ tarefa.descricao || "Tarefa sem descrição"}}
            </div>
            <div class="column">
                <Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
            </div>
        </div>
    </Box>

</template>

<style scoped>
    
    .column{
        color: var(--texto-primario)
    }
</style>

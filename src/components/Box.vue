<script lang="ts">
    import { defineComponent } from 'vue'

    export default defineComponent ({
        name:'Box',
    });

</script>

<template>
    <div class="box has-text-weight-bold">
        <slot></slot>
    </div>
</template>

<style scoped>
    .box{
        background-color: #3186CD;/* 7B2383 */
    }
</style>
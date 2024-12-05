<script setup>
    const props = defineProps(['tarefas']);
</script>

<template>
    <ul class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" v-bind:checked="tarefa.finalizada" v-bind:id="tarefa.titulo" type="checkbox" />
            <label class="ms-3" v-bind:class="{ done: tarefa.finalizada }" v-bind:for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>
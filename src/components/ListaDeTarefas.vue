<script setup>
const props = defineProps(['tarefas', 'listaTarefas']) 
</script>
<template>
    <span v-if="props.listaTarefas > 0">
        <ul class="list-group mt-4">
            <li class="list-group-item" v-for="tarefa in props.tarefas">
                <input @change="evento => tarefa.finalizada = evento.target.checked" :id="tarefa.titulo" type="checkbox"
                    :checked="tarefa.finalizada">
                <label :for="tarefa.titulo" class="ms-3" :class="{ done: tarefa.finalizada }">
                    {{ tarefa.titulo }}
                </label>
            </li>
        </ul>
    </span>
    <h2 v-else class="text-center pt-4">Você ainda não possui tarefas</h2>
</template>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>
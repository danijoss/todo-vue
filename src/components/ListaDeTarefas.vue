<script setup>
    const props = defineProps(['tarefas', 'tarefasPendentes', 'valorFiltro'])
</script>
<template>
    <ul class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
    <span v-if="props.tarefasPendentes === 0 && props.valorFiltro == 'pendentes'" >Você não possui tarefas pendentes</span>
</template>

<style scoped>

.done {
    text-decoration: line-through;
}

</style>
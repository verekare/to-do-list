<template lang="ts">

<div v-if="tasks.length > 0" >
    <div class="tasks">
        <h2 >To-dos</h2>
        <task-item
            v-for="task in tasks"
            :task="task"
            :key="task.id"
            @remove="$emit('remove', task)"
        />
    </div>
</div>
<div v-else class="tasks">
    <h2>
        Nothing to do yet.
    </h2>
</div>
    
</template>

<script>
import TaskItem from './TaskItem.vue';

export default {
    components: {TaskItem},
    props: {
        tasks: {
            type: Array,
            required: true
        }
    },
}
</script>


<style lang="scss" scoped>
* {
    color: whitesmoke;
    font-family: 'Avenir', sans-serif;
}
.tasks {
    margin: auto;
    max-width: 400px;
}
</style>
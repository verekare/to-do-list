<template>
    <form @submit.prevent>
        <my-input
            v-model="task.title"
            type="text"
            class="input" placeholder="a task to do"
        />
        <my-button 
        style="background: rgb(245, 245, 245);"
        @click="addTask">Add task
        </my-button>
    </form>
</template>
<script>
import MyButton from '@/components/UI/MyButton';
export default {
    components: {
        MyButton
    },
    data() {
        return {
            task: {
                title: '',
            }
        }
    },
    methods: {
        addTask() {    
            this.task.id = Date.now();
            this.$emit('add', this.task);
            this.task = {
                title: ''
            };
        }
    }
}
</script>
<style lang="scss">
    form {
        margin: auto;
        max-width: 400px;
        display: flex;
        flex-direction: column;
        gap: 8px;
    }
</style>
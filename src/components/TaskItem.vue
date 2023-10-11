<template>
<div class="task">
    <textarea disabled max-length="50" cols="40">{{ task.title }}</textarea>
    <div class="task__btns">
        <my-button class="task__btn">
            E
        </my-button>
        <my-button 
            @click="$emit('remove', task)"
            class="task__btn"
        >
            D
        </my-button>
    </div>
</div>
</template>


<script>
import MyButton from '@/components/UI/MyButton'

export default {
    components: {
        MyButton
    },
    props: {
        task: {
            type: Object,
            required: true
        }
    }
}
</script>


<style lang="scss">
textarea {
    background: none;
    min-width: 300px;
    border: none;
    border-radius: 15px;
    padding: 10px;
    font-family: Avenir, sans-serif;
    font-size: 1.1em;
    color: whitesmoke;
}
.task {
    padding: 10px;
    padding-left: 15px;
    margin-top: 20px;
    font-weight: 500;
    border: 2px solid whitesmoke;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    gap: 5px;
}
.task::selection {
    background-color: rgb(255, 164, 53);
}
.task__btns {
    display: flex;
    margin: auto;
    align-items: center;
    opacity: 0;
    transition: all .2s ease-out;
    overflow: visible;
    align-self: flex-end;
}
.task:hover .task__btns {
    opacity: 100;
}
</style>
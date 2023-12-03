<template>
<div class="task">
    <textarea :disabled="disabledEdit" max-length="50" cols="40">{{ task.title }}</textarea>
    <div class="task__utils">
        <my-button 
        style="background: none;"
        @click="$emit('remove', task)">
        <svg xmlns="http://www.w3.org/2000/svg" width="25" height="25" viewBox="0 0 25 25" fill="none">
            <circle cx="12.5" cy="12.5" r="12" stroke="white"/>
            <path d="M7.55029 7.55023L17.4498 17.4497" stroke="white" stroke-linecap="round"/>
            <path d="M17.4497 7.55023L7.55023 17.4497" stroke="white" stroke-linecap="round"/>
        </svg>
    </my-button>
    </div>
</div>
</template>


<script>
import MyButton from '@/components/UI/MyButton';
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


<style>
textarea {
    background: none;
    height: auto;
    min-height: 25px;
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
.task__utils {
    /* display: flex; */
    /* // margin-top: 5px; */
    opacity: 0;
    transition: all .2s ease-out;
    overflow: visible;
}
.task:hover .task__utils {
    opacity: 100;
}
</style>
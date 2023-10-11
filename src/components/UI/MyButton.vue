<template>
<button>
<slot></slot>
</button>
</template>

<script>
export default {
    name:'my-button'
}
</script>

<style>
    button {
        padding: 3px;
        margin-left: 5px;
        border: none;
        border-radius: 20px;
        background-color: whitesmoke;
        color: tomato;
        font-family: Avenir;
        font-weight: 500;
        text-transform: uppercase;
    }
    button:active {
        background-color: whitesmoke;
        color: tomato;
    }
</style>
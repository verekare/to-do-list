<template>
    <div class="dialog" v-if="show">
        <div class="dialog__content">
            <slot></slot>
        </div>
    </div>
</template>
<script>
export default {
    name: 'my-dialog',
    props: {
        show: {
            type: Boolean,
            default: false
        }
    }
}
</script>

<style scoped>
.dialog {
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    background: rgba(0, 0, 0, 0.5);
    position: fixed;
    display: flex;
}

.dialog__content {
    margin: auto;
    background-color: whitesmoke;
    border-radius: 12px;
    min-height: 100px;
    min-width: 300px;
}
</style>
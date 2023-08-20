<template>
    <button :class="[type]" :style="{ width: [width] + 'px', height: [height] + 'px' }">
        <slot></slot>
    </button>
</template>

<script>
export default {
    name: 'ButtonComponent',
    props: {
        type: String,
        width: String,
        height: String
    }
}
</script>

<style scoped>
button {
    cursor: pointer;
    transition: all .2s ease-in-out;
    box-sizing: border-box;
    border: 2px solid;
}

.primary {
    color: white;
    background-color: rgb(78, 90, 249);
    border-color: rgb(78, 90, 249);
    font-size: 16px;
}

.primary:hover,
.primary:focus {
    background-color: rgb(58, 70, 229);
    border-color: rgb(58, 70, 229);
}

.secondary {
    color: rgb(80, 80, 80);
    background-color: white;
    border-color: rgb(232, 232, 232);
    font-weight: bold;
}

.secondary:hover,
.secondary:focus {
    border-color: rgb(209, 209, 209);
}
</style>

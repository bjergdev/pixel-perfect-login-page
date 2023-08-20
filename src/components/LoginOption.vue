<template>
    <button>
        <img :src="getLogo" />
        <span>
            <slot></slot>
        </span>
    </button>
</template>

<script>
export default {
    name: 'LoginOption',
    props: {
        source: String,
        logo: String
    },
    computed: {
        getLogo() {
            const images = require.context('../assets/', false, /\.png$/);
            return images('./' + this.logo.toLowerCase() + '.png');
        }
    }
}
</script>

<style scoped>
button {
    display: flex;
    align-items: center;
    cursor: pointer;
    height: 48px;
    border: 2px solid rgb(232, 232, 232);
    background-color: white;
    color: rgb(32, 31, 36);
}

button:hover,
button:focus {
    border-color: rgb(209, 209, 209);
}

span {
    flex: 1;
    margin-left: -27px;
    font-size: 16px;
}
</style>

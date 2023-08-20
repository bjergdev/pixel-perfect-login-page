<template>
    <div id="app">
        <header class="topbar">
            <img src="./assets/logo.png" /><PButton type="secondary" width="80" height="36">Sign up</PButton>
        </header>
        <div class="login-section">
            <LoginLayout />
        </div>
    </div>
</template>

<script>
import LoginLayout from './layouts/Login.vue';
import PButton from './components/PButton.vue';

export default {
    name: 'App',
    components: {
        LoginLayout,
        PButton
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    padding: 32px 48px;
}

.topbar {
    display: flex;
    justify-content: space-between;
}

.login-section {
    display: flex;
    justify-content: center;
}

input {
    outline: none;
    border-style: solid;
}
</style>

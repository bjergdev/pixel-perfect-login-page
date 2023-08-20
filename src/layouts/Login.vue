<template>
    <div class="login">
        <h1>Log in</h1>
        <div class="container">
            <InputWithState placeholder="Sign in method" defaultValue="Password method" />
            <InputWithState placeholder="Email" isEmail />
            <PButton type="primary" height="48">Continue with email</PButton>
        </div>
        <h2 class="divider"><span>OR</span></h2>
        <div class="container">
            <LoginOption logo="google">Continue with Google</LoginOption>
            <LoginOption logo="microsoft">Continue with Microsoft</LoginOption>
        </div>
        <a class="forgot-password" href="#">Forgot password?</a>
    </div>
</template>

<script>
import InputWithState from '../components/InputWithState.vue';
import LoginOption from '../components/LoginOption.vue';
import PButton from '../components/PButton.vue';

export default {
    name: 'LoginLayout',
    components: {
        InputWithState,
        LoginOption,
        PButton
    }
}
</script>

<style scoped>
h1 {
    font-size: 39px;
    text-align: left;
    margin: 43px 0;
    color: rgb(32, 31, 36);
}

.login {
    display: flex;
    flex-direction: column;
    width: 402px;
}

.container {
    display: grid;
    gap: 25px;
}

.divider {
    margin: 45px 0;
    width: 100%;
    text-align: center;
    border-bottom: 1px solid rgb(232, 232, 232);
    line-height: 1px;
}

.divider span {
    color: rgb(133, 133, 133);
    background: white;
    padding: 0 10px;
    font-size: 16px;
}

.forgot-password {
    color: rgb(88, 87, 91);
    margin-top: 40px;
    font-size: 15px;
    text-underline-offset: 3px;
}
</style>

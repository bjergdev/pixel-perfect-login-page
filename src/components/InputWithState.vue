<template>
    <ValidationProvider v-slot="{ errors }">
        <div class="input-container">
            <input
                v-model="value"
                required
                :class="{
                    'error': errors.length || (isEmail && value.length && !value.includes('@')),
                    'blank': !value.length,
                    'unclickable': !isEmail
                }"
            />
            <span class="floating-label">{{ placeholder }}</span>
        </div>
    </ValidationProvider>
</template>

<script>
import { ValidationProvider } from 'vee-validate/dist/vee-validate.full.esm';

export default {
    name: 'InputWithState',
    components: {
        ValidationProvider
    },
    props: {
        type: String,
        placeholder: String,
        showTip: Boolean,
        defaultValue: String,
        isEmail: Boolean
    },
    created() {
        if (this.defaultValue) {
            this.value = this.defaultValue;
        }
    },
    data: function () {
        return {
            value: ''
        }
    }
}
</script>

<style scoped>
.input-container {
    position: relative;
}

.input-container:hover .unclickable {
    border-color: rgb(209, 209, 209);
}

input {
    width: 100%;
    height: 48px;
    padding-inline: 16px;
    box-sizing: border-box;
    font-size: 16px;
    background-color: rgb(242, 242, 242);
    border-color: rgb(242, 242, 242);
    transition: all .2s ease-in-out;
}

input.blank {
    background-color: rgb(242, 242, 242);
    border-color: rgb(242, 242, 242);
}

input:not(:focus):not(.error):hover {
    border-color: rgb(209, 209, 209);
}

input:not(:focus):not(.blank):not(.error):hover ~ .floating-label,
.input-container:hover input:not(:focus):not(.blank):not(.error) ~ .floating-label {
    color: rgb(32, 31, 36);
}

input.error {
    border-color: rgb(251, 73, 90);
}

input:focus {
    border-color: rgb(78, 90, 249);
}

input:focus ~ .floating-label,
input:not(:focus):valid ~ .floating-label {
  top: -8px;
  font-size: 14px;
  opacity: 1;
}

input:focus ~ .floating-label {
    color: rgb(78, 90, 249);
}

input.error:not(:focus):valid ~ .floating-label{
  color: rgb(251, 73, 90);
}

.floating-label {
  position: absolute;
  pointer-events: none;
  left: 10px;
  top: 15px;
  transition: 0.2s ease all;
  background-color: white;
  padding-inline: 8px;
  border-radius: 50%;
  color: rgb(133, 133, 133);
}

.unclickable {
    pointer-events: none;
}
</style>

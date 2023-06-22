<template>
    <div class="login-screen">
        <div class="login-parent">
            <div class="login-card">
                <div class="error-msg" v-if="_error">
                    {{ _error }}
                </div>
                <form @submit.prevent="onSubmit">
                    <div class="inputs">
                        <input type="text" class="login-input" placeholder="Email Address" v-model="form.email" />
                    </div>
                    <div class="inputs">
                        <input type="password" class="login-input" placeholder="Password" v-model="form.password" />
                    </div>
                    <div class="input-button">
                        <button type="submit" class="login-button">
                            <span v-if="isLoading"> Loading...</span>
                            <span v-else>Login</span>
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<style>
.login-screen {
    display: flex;
    height: 80vh;
    justify-content: center;
    flex-direction: column;
}

.login-parent {
    display: flex;
    justify-content: center;
}

.login-card {
    background: #ccc;
    box-shadow: 0px 2px 9px #0000001a;
    padding: 3rem;
    border-radius: 12px;
}

.error-msg {
    color: red;
    font-weight: 600;
    margin-bottom: 10px;
}

.inputs {
    margin-bottom: 13px;
}

.login-input {
    width: 18rem;
    padding: 0.3rem;
}

.input-button {
    text-align: center;
}

.login-button {
    padding: 0.4rem 5rem;
    background: indigo;
    color: #fff;
    font-size: 14px;
    cursor: pointer;
}
</style>

<script setup>
const url = "https://reqres.in/api/login"
const isLoading = ref(false);
const _error = ref(null);

const form = reactive({
    email: "eve.holt@reqres.in",
    password: "cityslicka",
});

async function onSubmit() {
    if (isLoading.value) return;

    isLoading.value = true;
    const { data, error } = await useFetch(url, {
        method: "post",
        body: form
    });

    isLoading.value = false;
    if (error.value) {
        _error.value = error.value.data.error;
        return;
    }

    const auth = useAuth();
    auth.value.isAuthenticated = true;
    navigateTo('/')
}

</script>
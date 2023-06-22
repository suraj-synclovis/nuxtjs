<template>
    <div class="login-screen">
        <div class="login-parent">
            <div class="login-card">
                <form @submit.prevent="onSubmit">
                    <div class="inputs">
                        <input type="text" class="login-input" placeholder="Email Address" v-model="form.email" />
                    </div>
                    <div class="inputs">
                        <input type="password" class="login-input" placeholder="Password" v-model="form.password" />
                    </div>
                    <div class="input-button">
                        <button type="submit" class="login-button">Login</button>
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
}
</style>

<script>
const url = "https://reqres.in/api/login"

const form = reactive({
    email: "eve.holt@reqres.in",
    password: "cityslicka",
})

function onSubmit() {
    const response = useFetch(url, {
        method: "post",
        body: form
    });
}

</script>
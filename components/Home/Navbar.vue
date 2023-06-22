<template>
    <nav class="nav">
        <div class="left-nav">
            <NuxtLink to="/">Home</NuxtLink>
            <NuxtLink to="/iphone">Iphones</NuxtLink>
            <p>Cart ({{ cart.length }})</p>
        </div>

        <div v-if="auth.isAuthenticated">
            <NuxtLink to="/profile">Profile</NuxtLink>
            <button class="logout-btn" @click="logout()">Logout</button>
        </div>

        <NuxtLink v-else to="/login">Login</NuxtLink>

    </nav>
</template>

<style>
.nav {
    background: purple;
    font-weight: 700;
    padding: 2rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.nav a {
    color: #fff;
    text-decoration: none;
}

.left-nav {
    display: flex;
    align-items: center;
    gap: 5rem;
}

.nav p {
    color: #fff;
}

.logout-btn {
    margin-left: 5rem;
    cursor: pointer;
}
</style>

<script setup>
import { useAuth } from '~/composables/states';

const cart = useCart();
const auth = useAuth();

function logout() {
    auth.value.isAuthenticated = false;
}
</script>
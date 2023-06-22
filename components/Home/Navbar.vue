<template>
    <nav class="nav">
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/about">About</NuxtLink>
        <NuxtLink to="/iphone">Iphones</NuxtLink>
        <NuxtLink to="/profile">Profile</NuxtLink>
        <NuxtLink to="/login">Login</NuxtLink>
        <p>Cart ({{ cart.length }})</p>
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

.nav p {
    color: #fff;
}
</style>

<script setup>
const cart = useCart();
</script>
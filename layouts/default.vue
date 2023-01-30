<script setup>
const user = useUser()

</script>

<template>
    <nav style="display: flex; gap: 10px">
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/movies">Movies</NuxtLink>
        <NuxtLink v-if="!user.isLoggedIn" to="/login">Login</NuxtLink>
        <NuxtLink v-else to="/" @click.prevent="user.isLoggedIn=false">Logout</NuxtLink>
    </nav>
    <slot></slot>
</template>
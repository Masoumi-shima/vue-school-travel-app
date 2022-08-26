<template>
    <div>
        <h1>Greeting, {{username}}!</h1>
        <button class="btn" @click="logout">Logout</button>
        <router-link :to="{name:'invoices'}">
            <button class="btn">Invoices</button>
        </router-link>
    </div>
</template>
<script>
export default {
    data() {
        return {
            username: window.user
        }
    },
    methods: {
        logout() {
            window.user = null
            this.$router.push({name:'login'})
        }
    }
}
</script>

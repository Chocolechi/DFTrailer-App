<template>
    <div class="container mt-5">
        <LoginApp />
        <FooterPage />
    </div>
</template>
<script>
import LoginApp from '../components/Login-app.vue'
import FooterPage from '../components/Footer-Page.vue'
export default {
    name:'LoginView',
    components:{
        LoginApp,
        FooterPage,
    }
}
</script>
<style scoped>

</style>
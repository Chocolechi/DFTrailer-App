<template>
    <div class="container">
        <EditItem />
        <FooterPage />
    </div>
</template>
<script>
import EditItem from '../components/Edit-Item.vue'
import FooterPage from '../components/Footer-Page.vue'

export default {
    name:'EditView',
    components:{
        EditItem,
        FooterPage,
    }
}
</script>
<style scoped>

</style>
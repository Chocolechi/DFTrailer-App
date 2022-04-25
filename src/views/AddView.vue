<template>
    <div class="container">
        <AddItem />
        <FooterPage />
    </div>
</template>
<script>
import AddItem from '../components/Add-Item.vue'
import FooterPage from '../components/Footer-Page.vue'

export default {
    name:'AddView',
    components:{
        AddItem,
        FooterPage,
    }
}
</script>
<style scoped>

</style>
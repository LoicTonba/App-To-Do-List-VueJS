<template>
    <div class="header-top">
        <p>{{ titre }}</p>
    </div>
</template>

<script>

    export default {
        name: 'Hea_der',
        data(){
            return{
                titre: 'La To-Do Liste !'
            }
        }
       
    }
</script>

<style scoped>
    .header-top {
        position: fixed;
        top: 0;
        height: 50px;
        background: #333;
        color:#f1f1f1;
        width: 100%;
        text-align: center;
        line-height: 50px;
        font-size: 25px;
    }
</style>

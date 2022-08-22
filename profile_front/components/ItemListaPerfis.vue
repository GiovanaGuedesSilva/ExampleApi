<template>
    <div class="item-perfis mb-2 pt-3 pb-3">
        <b-row>
            <b-col cols="2" class="d-flex align-items-center justify-content-center">
                <b-avatar class = "img" v-bind:src=img></b-avatar>
            </b-col>
            <b-col cols="10" class="d-flex align-items-center justify-content-center">
                <NuxtLink :to="`/${idPerfil}}`">{{perfil}}</NuxtLink>
            </b-col>          
        </b-row>
    </div>
</template>

<script>
   export default {
    name: 'PerfilPage',
    props: ["idPerfil","perfil", "img"]
   }
</script>

<style>
    .item-perfis{
        background-color: rgb(204, 204, 204);
        border: solid 0.5px rgb(107, 107, 107);
        border-radius: 10px;
        margin-bottom: 20px;
    }
    
    a{
        color: black;
    }

    .img{
        width: 70px;
        height: 70px;
        margin-left: 50px;
        border: solid white 0.5px;
    }

    h1{
        text-align: center;
        margin-bottom: 40px;
    }

</style>

<template>
  <div class="page-holder bg-gray-100 mt-5">
      <b-container class="bv-example-row">
        <h1>
          Perfis
        </h1>        

        <div :key="perfil.id" v-for="perfil in perfis">
          <ItemListaPerfis 
            :idPerfil="perfil.id"
            :perfil="perfil.nome"
            :img="perfil.foto">
          </ItemListaPerfis>
        </div>
      </b-container>
      <div class="text-center">
        <button clas = "text-center" type = "button" v-on:click = "testeConsulta"> Clique em mim </button>
      </div>
      <div id = "teste"> </div>
  </div>
</template>

<script>
import ItemListaPerfis from '~/components/ItemListaPerfis.vue';
export default {
    name: "IndexPage",
    data() {
        return {
            /*perfis: [
                
                {
                    id: 2,
                    nome: "Giorno Giovanna",
                    frase: "Deus te abençoe.",
                    localizacao: "Brasil, São Paulo",
                    foto: "https://i.pinimg.com/originals/c2/df/6f/c2df6f798dc537b9d835fcfa75c3693b.jpg",
                    seguidores: 450,
                    seguindo: 20
                },
                {
                    id: 3,
                    nome: "Ednaldo Pereira",
                    frase: "Deus te ilumine.",
                    localizacao: "Brasil, Atibaia",
                    foto: "https://i.scdn.co/image/ab6761610000e5eb9319d939accc1f1e22155955",
                    seguidores: 450,
                    seguindo: 20
                },
                {
                    id: 4,
                    nome: "Messi Careca",
                    frase: "Deus te ouça.",
                    localizacao: "Brasil, Campinas",
                    foto: "https://i.pinimg.com/736x/23/61/5c/23615ce774a4264fc334b1a5cd422de4.jpg",
                    seguidores: 450,
                    seguindo: 20
                }

                
            ],*/
            perfis: [], // Lista de perfis vazia
            teste: "",
        };
    },
    methods:{
      testeConsulta(){
        this.$axios.get("/perfil").then( function(response){
          const div = document.querySelector("#teste");
          div.innerHTML = JSON.stringify(response.data);
          // parse -> json para js
        });
      }
    },

    // Executado quando o vue/página é criado(a)
    async mounted(){
      const response = await this.$axios.get("/perfil");
      this.perfis = response.data;
    },

    components: { ItemListaPerfis }
}
</script>

<style>

  body {
    font-family: 'Montserrat', sans-serif;
    font-size: 16px;
    color: black;
  }

  button{
    background-color: rgb(53, 53, 53);
    color: white;
    padding: 10px;
    border-radius: 10px;
    margin: auto;
    margin-top: 30px;
  }

</style>
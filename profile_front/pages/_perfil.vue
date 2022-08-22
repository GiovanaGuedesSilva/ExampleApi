<template>
  <div class="page-holder bg-gray-100 mt-5">
      <b-container class="bv-example-row">
        <b-row >
          <b-col cols="12" class="d-flex justify-content-center">
            <b-avatar v-bind:src=foto size="12rem"></b-avatar>
          </b-col>
          <b-col cols="" class="bg-info  mt-2">
            <div class="text-center mb-3 title text-secundario font-weight-bold">
                <span>@</span>{{pagina}}
            </div>
            <div class="text-center mb-3">
              <span>{{ frase }}</span>
            </div>
            <div class="text-center mb-3">
              <b-icon icon="geo-alt-fill" scale="1.5"></b-icon> {{ localizacao }}  
            </div>
            <div class="text-center mb-3">
              <span>{{ frase }}</span>
            </div>
          </b-col>
        </b-row>
        <b-row >
          <b-col class="text-center">           
            <span class="font-weight-bold">Seguidores: </span>{{seguidores}}
          </b-col>
          <b-col class="text-center">
            <span class="font-weight-bold">Seguindo: </span>{{seguindo}}
          </b-col>
        </b-row>
      </b-container>
  </div>
</template>

<script>
export default {
  name: 'PerfilPage',
  data() {
    return {
      nome: "Messi Careca",
      frase: "Deus te ouça.",
      localizacao: "Brasil, Campinas",
      foto: "https://i.pinimg.com/736x/23/61/5c/23615ce774a4264fc334b1a5cd422de4.jpg",
      seguidores: 450,
      seguindo: 20
    }
  },
  computed:{
    pagina(){
      return this.nome.replace(" ", "").toLocaleLowerCase();
    }
  }
}
</script>

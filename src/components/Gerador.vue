<template>
  <div class="col-12 py-5">
    <div class="form-group">
      <label for="">NÚMERO</label>
    <input type="text" v-model="numero" class="form-control" name="" id="">
    </div>
    <div class="form-group">
      <label for="">MENSAGEM</label>
    <input type="text" v-model="mensagem" class="form-control" name="" id="">
    </div>
    <button @click="GerarLink" class="btn btn-primary btn-lg btn-block">GERAR LINK</button>
  {{url}}
  </div>
</template>

<script>
export default {
  name: "Gerador",
  data: function() {
    return {
      numero: "",
      mensagem: "",
      url: "",
    };
  },
  methods: {
    GerarLink: function() {
      // Substitui tudo o que nã é numero por ''
      let n = this.numero.replace(/[^0-9]/g, '');
      // Limpa a mensagem
      let m = encodeURI(this.mensagem);
      // Link do whatsapp
      this.url = `http://wa.me/send?phone=${n}&text=${m}`;
      // Chama a página about
      this.$router.push({
        name: "Resultado",
        params: {
          link: this.url,
      },
      });
    },
  },
};
</script>

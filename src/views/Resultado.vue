<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <div class="form-group">
          <label for="exampleFormControlTextarea1">SEU LINK FOI GERADO</label>
          <textarea
            class="form-control"
            id="url"
            rows="3"
            v-model="$route.params.link"
          ></textarea>
        </div>
      </div>
    </div>
    <div class="col-12 d-flex justify-content-around">
      <!-- data-clipboard indica o que será copiado -->
      <button class="btn btn-success" id="copiar" data-clipboard-target="#url">COPIAR</button>
      <a target="_blank" :href="$route.params.link"><button class="btn btn-warning">TESTAR</button></a>
      <router-link to="/" class="btn btn-danger">VOLTAR</router-link>
    </div>
  </div>
</template>

<script>
import ClipboardJS from "clipboard";
// Vai estar em todo botão com id  copiar
new ClipboardJS("#copiar")
export default {};
</script>

<template>
  <q-page>
    <q-page-container>
  <div class="q-pa-md">
    <q-form style="width:80%"
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md formulario"
    >
    <div class="row ">
      <q-input
      class="dados"
        filled
        v-model="name"
        label="Nome Completo *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Preencha seu nome corretamente']"
      />
    </div>

    <div class="row">
      <q-input
      class="dados"
        filled
        label="Ponto Comercial *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Preencha seu Ponto Comercial']"
      />
    </div>

    <div class="row">
      <q-input
        filled
        class="forms"
        label="Endereco *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Preencha seu endereco']"
      />

      <q-input
        filled style="margin-left: 80px"
        label="Numero / Complemento"
        class="forms"
      />
    </div>

    <div class="row">
      <q-input style="margin-bottom: 19px"
        filled
        class="forms"
        label="Estado *"
        />

      <q-input style="margin-left: 80px"
        filled
        label="Cidade *"
        class="forms"
        />
    </div>

    <div class="row">
      <q-input style="margin-bottom: 19px"
        filled
        label="Telefone *"
        class="forms"
        type="number"
      />

      <q-input style="margin-left: 80px"
        filled
        label="CPF *"
        type="number"
        class="forms"
      />
    </div>

    <div class="row">
      <q-input
      class="forms"
        filled
        label="Email *"
        :value="email"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Preencher o email corretamente']"
      />

      <q-input style="margin-left: 80px"
        filled
        class="forms"
        label="Repetir email *"
        :value="email"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Preencher o email corretamente']"
      />
    </div>

    <div class="row">
      <q-input
        filled
        class="forms"
        label="Senha *"
        type="password"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Minimo de 8 caracteres']"
      />

      <q-input style="margin-left: 80px"
        filled
        class="forms"
        label="Repetir Senha *"
        type="password"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Minimo de 8 caracteres']"
      />
    </div>

      <div align="center">
        <q-btn class="botao-cadastrar" label="CADASTRAR" type="submit"/>
      </div>
    </q-form>

  </div>
    </q-page-container>
  </q-page>
  </template>

<script>
export default {
  data () {
    return {
      name: null,
      age: null,

      accept: false
    }
  }
}
</script>

<style lang="stylus">

.formulario{
  margin:8%;
}

.dados{
  width:98%;
}

.forms{
  width 45% ;
}

.botao-cadastrar{
  width: 260px;
    height: 56px;
    background-color: #2e4e06 ;
    border-radius: 8px;
    color:white;
    font-size: 18px;
    border:0;
    margin-top: 40px;
    transition:background-color 400ms;
}
</style>

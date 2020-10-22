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
        :rules="[val => val !== null && val !== '' || 'Digite seu nome compleyo']"
      />
    </div>

    <div class="row">
      <q-input
      class="dados"
        filled
        label="Ponto Comercial *"
        lazy-rules
        v-model="ponto"
        :rules="[val => val !== null && val !== '' || 'Digite seu Ponto Comercial']"
      />
    </div>
 <div class="row">
      <q-input
      class="forms"
        filled
        label="Endereco *"
        :value="email"
        lazy-rules
      v-model="endereco"
        :rules="[val => val !== null && val !== '' || 'Digite seu endereco']"
      />

      <q-input style="margin-left: 80px"
        filled
        class="forms"
        label="Número / Complemento *"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
    </div>
    <div class="row">
      <q-input
      class="forms"
        filled
        label="Estado *"
        :value="email"
        lazy-rules
        v-model="estado"
        :rules="[val => val !== null && val !== '' || 'Digite seu Estado']"
      />

      <q-input style="margin-left: 80px"
        filled
        class="forms"
        label="Cidade *"
        v-model="cidade"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Digite sua Cidade']"
      />
    </div>
<div class="row">
      <q-input
      class="forms"
        filled
        label="Telefone *"
        type="number"
        lazy-rules
        v-model="telefone"
        :rules="[val => val !== null && val !== '' || 'Digite o seu telefone']"
      />

      <q-input style="margin-left: 80px"
        filled
        class="forms"
        type="number"
        label="CPF *"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Digite o seu CPF']"
      />
    </div>
    <div class="row">
      <q-input
      class="forms"
        filled
        label="Email *"
        :value="email"
        lazy-rules
        v-model="email"
        :rules="[val => val !== null && val !== '' || 'Preencher o email corretamente']"
      />

      <q-input style="margin-left: 80px"
        filled
        class="forms"
        label="Repetir email *"
        :value="email"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Preencher o email corretamente']"
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
      ponto: null,
      model: '',
      endereco: null,
      email: null,
      cidade: null,
      estado: null,

      accept: false
    }
  },
  methods: {
    reset () {
      this.$refs.input.resetValidation()
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

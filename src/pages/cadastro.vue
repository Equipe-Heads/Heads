<template>
  <q-page>
    <q-page-container>
      <div class="q-pa-md">
        <q-form style="width:80%"
          @submit="onSubmit"
          @reset="onReset"
          class="q-gutter-md formulario"
        >
      <div class="q-pa-md q-mb-xl" style="border: 1px solid grey">
        <p style="font-size:30px;">Dados Cadastrais</p>
      <div class="justify-between row ">
      <q-input style="width:71%"
        filled
        v-model="name"
        label="Nome / Razão Social"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
      <q-input style="width:25%"
        filled
        label="Telefone"
        type="number"
        v-model="telefone"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
    </div>
    <div class="justify-between row">
      <q-input style="width:50%"
      class=""
        filled
        label="Rua, Avenida, Praça, etc... (ou Somente o CEP)"
        v-model="endereco"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
      <q-input style="width:15%"
        filled
        label="Número"
        v-model="numeroEndereco"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />

      <q-input style="width:29%"
        filled
        label="Complemento"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
</div>
<div class="justify-between row">
  <q-input style="width:33%"
        filled
        label="Bairro"
      v-model="bairro"
      lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
      <q-input style="width:20%"
        filled
        label="CEP"
        type="number"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />

      <q-input style="width:29%"
        filled
        v-model="cidade"
        label="Cidade"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />

      <q-input style="width:10%"
        filled
        v-model="estado"
        label="UF"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
</div>
</div>

 <div class="q-pa-md q-mb-xl" style="border: 1px solid grey">
      <p style="font-size:30px;">Documentação</p>
      <p class="q-ma-xs" style="font-size:20px;">Pessoa</p>
      <q-radio unchecked-icon="visibility_off" checked-icon="visibility" class="q-mr-sm" color="green" v-model="shape" val="line" label="Fisica" />
      <q-radio color="green" v-model="shape" val="rectangle" label="Juridica" />

  <div class="pessoa-fisica row justify-between q-mt-lg" >
    <q-input  style="width:25%"
          filled
          type="number"
          label="CPF"
          v-model="cpf"
          lazy-rules
          :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
        />
    <q-input style="width:20%"
        filled
        type="number"
        label="Reg. Identidade"
        v-model="identidade"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
    <q-input style="width:25%"
        filled
        type="number"
        label="Org. Expeditor"
        v-model="orgao"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
    <q-input style="width:20%"
        filled
        v-model="dataexp"
        type="number"
        label="Data Exp."
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
  </div>

<div class="pessoa-juridica " >
  <div class="row">
    <q-input style="width:100%" class=""
        filled
        v-model="responsavel"
        label="Nome Completo do Responsável"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
  </div>

  <div class="justify-between row">
    <q-input  style="width:34%"
      filled
      type="number"
      label="CNPJ"
      v-model="cnpj"
      lazy-rules
      :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
    />
    <q-input style="width:30%"
      filled
      type="number"
      label="Inscrição Estadual"
      lazy-rules
      :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
    />
    <q-input style="width:30%"
      filled
      type="number"
      label="Inscrição Municipal"
      lazy-rules
      :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
    />
  </div>
</div>
</div>

<div class="q-pa-md" style="border: 1px solid grey">
  <p style="font-size:30px;">Login</p>
      <div class="justify-between row ">
        <q-input style="width:47%"
        filled
        label="Email"
        :value="email"
        v-model="email"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
        <q-input style="width:47%"
        filled
        class=""
        label="Repetir email"
        :value="email"
        v-model="email2"
        lazy-rules
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
      </div>

      <div class="justify-between row">
      <q-input style="width:47%"
        filled
        v-model="senha"
        label="Senha"
        type="password"
        lazy-rules
        :rules="[
          val => !!val || 'Campo Obrigatório',
          val => val.length >= 6 || 'Mínimo de 6 caracteres',
        ]"
        />

      <q-input style="width:47%"
        filled
        v-model="senha2"
        label="Repetir Senha"
        type="password"
        lazy-rules
        :rules="[
          val => !!val || 'Campo Obrigatório',
          val => val.length >= 6 || 'Mínimo de 6 caracteres',
        ]"
        />
    </div>
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
      telefone: null,
      endereco: null,
      numeroEndereco: null,
      bairro: null,
      cep: null,
      cidade: null,
      estado: null,
      cpf: null,
      identidade: null,
      responsavel: null,
      cnpj: null,
      email: null,
      email2: null,
      senha: '',
      senha2: '',
      accept: false,
      shape: 'line'
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

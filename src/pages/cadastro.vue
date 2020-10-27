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
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
      <q-input style="width:25%"
        filled
        label="Telefone"
        type="number"
        v-model="telefone"
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
    </div>
    <div class="justify-between row">
      <q-input style="width:50%"
      class=""
        filled
        label="Rua, Avenida, Praça, etc... (ou Somente o CEP)"
        v-model="endereco"
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
      <q-input style="width:15%"
        filled
        label="Número"
        v-model="numeroEndereco"
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />

      <q-input style="width:29%"
        filled
        label="Complemento"
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
</div>
<div class="justify-between row">
  <q-input style="width:33%"
        filled
        label="Bairro"
      v-model="bairro"
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
      <q-input style="width:20%"
        filled
        label="CEP"
        type="number"
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />

      <q-input style="width:29%"
        filled
        v-model="cidade"
        label="Cidade"
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />

      <q-input style="width:10%"
        filled
        v-model="estado"
        label="UF"
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
</div>
</div>

 <div class="q-pa-md q-mb-xl" style="border: 1px solid grey">
      <p style="font-size:30px;">Documentação</p>
      <p class="q-ma-xs" style="font-size:20px;">Pessoa</p>
      <q-radio class="q-mr-sm" color="green" v-model="shape" :value="true" val="line" label="Fisica" />
      <q-radio color="green" v-model="shape" val="rectangle" label="Juridica" />

  <div class="pessoa-fisica row justify-between q-mt-lg" >
    <q-input  style="width:25%"
          filled
          type="number"
          label="CPF"
          v-model="cpf"
          :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
        />
    <q-input style="width:20%"
        filled
        type="number"
        label="Reg. Identidade"
        v-model="identidade"
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
    <q-input style="width:25%"
        filled
        type="number"
        label="Org. Expeditor"
        v-model="orgao"
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
    <q-input style="width:20%"
        filled
        v-model="dataexp"
        type="number"
        label="Data Exp."
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
  </div>

<div class="pessoa-juridica " >
  <div class="row">
    <q-input style="width:100%" class=""
        filled
        v-model="responsavel"
        label="Nome Completo do Responsável"
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
  </div>

  <div class="justify-between row">
    <q-input  style="width:34%"
      filled
      type="number"
      label="CNPJ"
      v-model="cnpj"
      :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
    />
    <q-input style="width:30%"
      filled
      type="number"
      label="Inscrição Estadual"
      :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
    />
    <q-input style="width:30%"
      filled
      type="number"
      label="Inscrição Municipal"
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
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
        <q-input style="width:47%"
        filled
        class=""
        label="Repetir email"
        :value="email"
        v-model="email2"
        :rules="[val => val !== null && val !== '' || 'Campo Obrigatório']"
      />
      </div>

      <div class="justify-between row">
      <q-input style="width:47%"
        filled
        v-model="senha"
        label="Senha"
        type="password"
        :rules="[
          val => !!val || 'Campo Obrigatório',
          val => val.length > 8 || 'Mínimo de 8 caracteres',
        ]"
        />

      <q-input style="width:47%"
        filled
        v-model="senha2"
        label="Repetir Senha"
        type="password"
        :rules="[
          val => !!val || 'Campo Obrigatório',
          val => val.length > 8 || 'Mínimo de 8 caracteres',
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

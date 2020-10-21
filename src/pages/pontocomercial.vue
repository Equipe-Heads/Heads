<template>
    <q-page>
        <q-page-container>
        <div class="row" align ="center">
        <div class="col">
            <q-input
            class="campopesquisa"
            color="black"
            bg-color="white"
        v-model="search"
        debounce="500"
        outlined
        placeholder="Pesquisar"
      >
        <template v-slot:append>
          <q-btn
          color="green-10"
          class="cursor-pointer botaolupa" icon="search"  />
        </template>
      </q-input>
      </div>
      <div class="col">
            <template>
            <div class="div-botoes">
            <q-btn to="/cadastro" class="botoesauxiliares" color="green-10" style=" color: white; margin-right:30px;" label="CADASTRE-SE" />
            <q-btn class="botoesauxiliares" color="green-10" style="color: white" label="ENTRAR" />
            </div>
      </template>
      </div>
      </div>
      </q-page-container>
    </q-page>
</template>

<style lang="stylus">

.campopesquisa{
    margin-top 100px;
    margin-left 150px;
    width 80%;
    }

.botaolupa{
    height 40px;
    }

.div-botoes{
    margin-top 105px;
    }

.botoesauxiliares{
    width 130px;
    height 45px;
    margin-right 150px;
    }

</style>

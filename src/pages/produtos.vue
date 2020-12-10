<template>
    <q-page>
        <q-page-container>
        <div class="row" align ="margin-left">
        <div class="col">
            <q-input
            class="campodepesquisa"
            color="black"
            bg-color="white"
        v-model="search"
        debounce="500"
        outlined
        placeholder="Pesquisar"
      >
      <template>
  <div class="fixed">
    <q-option-group
      :options="options"
      label="Notifications"
      type="radio"
      v-model="group"
    />
  </div>
</template>
        <template v-slot:append>
          <q-btn
          color="green-10"
          class="cursor-pointer botaolupa" icon="search"  />
        </template>
      </q-input>

      </div>
    </div>
  </q-page-container>
</q-page>
</template>

<script>
export default {
  data () {
    return {
      group: null,
      options: [
        { label: 'Produto', value: 'bat', color: 'green' },
        { label: 'Local', value: 'friend', color: 'green' },
        { label: 'Categoria', value: 'upload', color: 'green' }
      ]
    }
  }
}
</script>
<style lang="stylus">

.campodepesquisa{
    margin-top 100px;
    margin-left 150px;
    width 40%;
    }

.botaolupa{
    height 40px;
    }

.fixed{
  margin-left 550px;
}
</style>

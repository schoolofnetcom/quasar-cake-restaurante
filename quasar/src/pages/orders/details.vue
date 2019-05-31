<template>
  <q-page padding>
    <h1 class="q-display-2">
      Detalhes do pedido
    </h1>

    <q-card v-for="i in 4" :key="i" class="q-mb-sm">
      <q-card-main class="row">
        <div class="col-md-1 col-xs-2">
          <img src="~assets/avatar.png" alt="" style="width:50px" class="round-borders">
        </div>
        <div class="col flex items-center">
          Nome do produto
        </div>
        <div class="col-md-4 flex items-center justify-end">
          1
        </div>
        <div class="col-2 flex items-center justify-end">
          R$ 10,00
        </div>
      </q-card-main>
    </q-card>

    <div class="row">
      <q-card class="col-xs-12 col-md-6 offset-md-6 text-black text-right" color="grey-3">
        <q-card-main>
          Entrega: R$ 10,00
        </q-card-main>
        <q-card-main>
          Pedido: R$ 40,00
        </q-card-main>
        <q-card-main>
          Total: R$ 50,00
        </q-card-main>
        <q-card-actions class="flex justify-end">
          <q-btn color="green" label="Acompanhar" :to="'/order/' + $route.params.id"/>
        </q-card-actions>
      </q-card>
    </div>
  </q-page>
</template>

<script>
export default {
  // name: 'PageName',
};
</script>

<style>
</style>

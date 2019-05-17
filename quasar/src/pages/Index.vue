<template>
  <q-page padding class="bg-food">
    <div class="flex flex-center">
      <h1 class="q-display-3 text-center q-py-xl">Você quer comer o que?</h1>
    </div>

    <div class="row gutter-md">
      <div class="col-xs-12 col-md-4">
        <q-card color="green">
          <q-card-title>
            <q-icon name="location_on"/> Usar minha localização atual
          </q-card-title>
          <q-card-separator/>
          <q-card-main>
            Próximo de ...
          </q-card-main>
          <q-card-actions>
            <q-btn to="/list-restaurants" flat label="Ver restaurantes"/>
          </q-card-actions>
        </q-card>
      </div>

      <div class="col-xs-12 col-md-4">
        <q-card color="orange">
          <q-card-title>
            <q-icon name="account_box"/> Acessar sua conta
          </q-card-title>
          <q-card-separator/>
          <q-card-main>
            Você pode pedir usando um endereço já existem acesse sua conta
            para começar
          </q-card-main>
          <q-card-actions>
            <q-btn to="/list-restaurants" flat label="Acessar conta"/>
          </q-card-actions>
        </q-card>
      </div>

      <div class="col-xs-12 col-md-4">
        <q-card color="primary">
          <q-card-title>
            <q-icon name="fastfood"/> Escolher localização
          </q-card-title>
          <q-card-separator/>
          <q-card-main>
            <q-btn
              to="/list-restaurants"
              color="white"
              text-color="primary"
              size="md"
              class="q-mr-md q-mb-md"
              :label="place"
              v-for="(place, index) in places"
              :key="index"
            />
          </q-card-main>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<style>
.bg-food {
  background: url("~assets/food-bg.jpg") no-repeat;
  background-size: contain;
}
</style>

<script>
export default {
  name: 'PageIndex',
  data() {
    return {
      places: [
        'CIDADE 1',
        'CIDADE 2',
        'BAIRRO 1',
        'BAIRRO 2',
        'BAIRRO 3',
      ],
    };
  },
};
</script>

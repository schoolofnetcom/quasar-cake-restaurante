<template>
  <q-page padding>
    <h1 class="q-display-2">
      Editando restaurante
    </h1>

    <form @submit.prevent="submit()" class="row gutter-md">
      <div class="col-12">
        <q-field icon="label">
          <q-input
            type="text"
            v-model="data.title"
            float-label="Nome do restaurante"
            autofocus/>
        </q-field>
      </div>

      <div class="col-12">
        <q-field icon="insert_photo">
          <q-input
            type="text"
            v-model="data.photo"
            float-label="Foto do restaurante"/>
        </q-field>
      </div>

      <div class="col-6">
        <q-field icon="timer">
          <q-input
            type="text"
            v-model="data.delivery_time"
            float-label="Tempo de entrega"/>
        </q-field>
      </div>

      <div class="col-6">
        <q-field icon="attach_money">
          <q-input
            type="text"
            v-model="data.delivery_price"
            float-label="Valor de entrega"/>
        </q-field>
      </div>

      <div class="col-12">
        <h2 class="q-display-1">Endereço</h2>
        <address-fields v-model="address"></address-fields>
      </div>

      <div class="col">
        <q-btn type="submit" color="primary" class="q-my-md q-mr-sm">Salvar</q-btn>
        <q-btn type="submit" color="secondary" class="q-my-md" to="/restaurants">Voltar</q-btn>
      </div>
    </form>
  </q-page>
</template>

<script>
import AddressFields from '../../components/address_fields';

export default {
  data() {
    return {
      data: {
        title: 'Nome do resstaurante',
        delivery_time: '10 minutos',
        delivery_price: '10,00',
      },
      address: {
        cep: '11676085',
        address: 'R. Fulano',
        number: '123',
        complement: 'Casa',
        neiborhood: 'Centro',
        city: 'Caraguatatuba',
        state: 'SP',
      },
    };
  },
  components: {
    'address-fields': AddressFields,
  },
  methods: {
    submit() {
      this.$q.notify({
        message: 'Restaurante alterado com sucesso',
        type: 'positive',
      });
    },
  },
};
</script>

<style>
</style>

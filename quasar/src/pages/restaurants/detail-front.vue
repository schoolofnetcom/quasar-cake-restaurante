<template>
  <q-page padding>
    <h1 class="q-display-2">
      Nome do restaurante
    </h1>
    <p class="q-mb-lg">
      <span class="text-amber"><q-icon name="star"/> 3.5</span> |
      <span class="text-grey">Entrega em 30-40 min - valor da entrega: R$ 5,00</span>
    </p>
    <div class="row gutter-lg">
      <div class="col-xs-12 col-md-6" v-for="i in 5" :key="i">
        <q-card>
          <q-card-media>
            <img src="~assets/food.jpg">
          </q-card-media>
            <q-card-title>
              Nome do prato
              <span slot="subtitle">R$ 15,00</span>
            </q-card-title>
          <q-card-separator/>
          <q-card-main>
            Aqui teremos uma descrição do prato, com ingrediantes (por exemplo)
          </q-card-main>
          <q-card-actions>
            <q-btn flat color="primary" label="PEDIR" @click="order()"/>
          </q-card-actions>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      opt: [],
    };
  },
  methods: {
    order() {
      this.$q.dialog({
        title: 'Confirmar pedido',
        options: {
          type: 'checkbox',
          model: this.opt,
          items: [
            { label: 'Opção 1', value: 1 },
            { label: 'Opção 2', value: 2 },
            { label: 'Opção 3', value: 3 },
          ],
        },
      }).then((data) => {
        this.opt = data;
      });
    },
  },
};
</script>

<style>
</style>

<template>
  <q-page padding>
    <h1 class="q-display-2">
      Seus restaurantes
    </h1>

    <q-table
      title="Restaurantes"
      :data="tableData"
      :columns="columns"
    >
      <q-tr slot="body" slot-scope="props">
        <q-td key="id">
          {{ props.row.id }}
        </q-td>
        <q-td key="title" class="text-left">
          {{ props.row.title }}
        </q-td>
        <q-td key="actions" class="text-right">
          <q-btn color="secondary" size="sm" class="q-mr-sm"
            :to="'/restaurant/' + props.row.id + '/detail'">+ detalhes</q-btn>
          <q-btn color="primary" size="sm"
            :to="'/restaurant/' + props.row.id + '/edit'">editar</q-btn>
        </q-td>
      </q-tr>
    </q-table>

    <q-btn color="primary" to="/new-restaurant" class="q-my-md">Novo restaurante</q-btn>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      tableData: [
        {
          id: 1,
          title: 'Nome do restaurante',
        },
        {
          id: 2,
          title: 'Outro restaurante',
        },
      ],
      columns: [
        {
          field: 'id',
          label: '',
        },
        {
          field: 'title',
          label: 'Título',
        },
      ],
    };
  },
  mounted() {
    if (this.tableData.length === 0) {
      this.$router.push('/new-restaurant');
    }
  },
};
</script>

<style>
</style>

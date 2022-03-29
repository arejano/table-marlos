<script>
export default {
  props: ["table_setup"],
  data() {
    return {};
  },
  methods: {
    existeTag() {
      return this.table_setup.headers.includes(" ");
    },
    editar(i) {
      console.log(i);
    },
    remover(i) {
      console.log(i);
    },
  },
};
</script>

<template>
  <table class="border">
    <thead>
      <tr>
        <th v-for="header in table_setup.headers" :key="header">
          {{ header }}
        </th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="data in table_setup.table" :key="data">
        <td v-for="key in table_setup.keys" :key="key">{{ data[key] }}</td>
        <!-- TODO: Descobrir qual a key ou função que retorna a tag -->
        <td v-if="existeTag()">{{ data["open_cart_period_end"] }}</td>
        <td>
          <button @click="editar(data.id)">E</button>
          <button @click="remover(data.id)">X</button>
        </td>
      </tr>
    </tbody>
  </table>

  <!-- {{table}} -->
</template>

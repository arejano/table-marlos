<script setup lang="ts">
import TableComponent from "@/components/TableComponent.vue";
import { ApiClient } from "../services/ApiClient.js"

const api = new ApiClient();

const table_setup = {
  headers: ["Nome", "Campanha", " ", "Ações"],
  keys: ["launch_name", "campaign_name"],
  table: api.get(),
};

</script>

<template>
  <main>
    <TableComponent :table_setup="table_setup" />
  </main>
</template>

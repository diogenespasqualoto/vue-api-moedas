<template>
  <table class="table">
    <thead>
      <tr>
        <th>Cód</th>
        <th>Nome</th>
        <th>Máximo</th>
        <th>Minímo</th>
        <th>Variação</th>

        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(quote, key) in quotes" :key="key">
        <td>{{ key }}</td>
        <td>{{ quote.name }}</td>
        <td>{{ quote.high }}</td>
        <td>{{ quote.low }}</td>
        <td>
          <span
            class="label label-rounded text-small"
            :class="{
              'label-error': quote.pctChange < 0,
              'label-success': quote.pctChange > 0,
            }"
          >
            {{ quote.pctChange }} %
          </span>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: { quotes: { type: Object, required: true } },
};
</script>

<style scoped>
</style>

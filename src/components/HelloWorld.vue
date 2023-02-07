<template>
  <div class="table">
    <thead>
      <tr>
        <th>Cóp</th>
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
        
          <span></span>

        </td>
      </tr>
    </tbody>
  </div>
</template>

<script>
export default {
  props: { quotes: { type: Object, required: true } },
};
</script>
<style scoped></style>

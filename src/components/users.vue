<template>
  <table v-if="value.length" :class="$style.table">
    <thead>
      <tr>
        <th>Name</th>
        <th>Username</th>
        <th>Email</th>
        <th>Phone</th>
        <th>Website</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="{ name, username, email, phone, website } in value">
        <td>{{ name }}</td>
        <td>{{ username }}</td>
        <td>{{ email }}</td>
        <td>{{ phone }}</td>
        <td>{{ website }}</td>
      </tr>
    </tbody>
  </table>
  <template v-else>
    No users found.
  </template>
</template>

<style lang="scss" module>
table {
  border-spacing: 0;
  border-collapse: collapse;

  th {
    font-weight: bold;
    font-size: 1.5em;
  }

  th,
  td {
    padding: 0.5em;
    text-align: left;
    border: solid 1px;
  }
}
</style>

<script setup>
const props = defineProps({
  value: { type: Array, required: true },
});
</script>

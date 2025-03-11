<template>
  <div>
    <h2>Open Source</h2>
    <button @click="$emit('open-modal')">Add</button>
    <table border="1">
      <thead>
        <tr>
          <th>ID</th>
          <th>Name</th>
          <th>City</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="student in students" :key="student.id">
          <td>{{ student.id }}</td>
          <td>{{ student.name }}</td>
          <td>{{ student.city }}</td>
        </tr>
      </tbody>
    </table>
    
  </div>
</template>

<script>
export default {
  props: ["students"],
};
</script>

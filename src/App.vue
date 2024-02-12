<template>
  <div>
    <table class="user-table">
      <thead>
        <tr>
          <th>ID</th>
          <th>Name</th>
          <th>Email</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id" @click="showDetails(user)">
          <td>{{ user.id }}</td>
          <td>{{ user.name }}</td>
          <td>{{ user.email }}</td>
        </tr>
      </tbody>
    </table>

    <!-- Display customer details -->
    <div v-if="selectedUser" class="details">
      <h2>Customer Details</h2>
      <p><strong>ID:</strong> {{ selectedUser.id }}</p>
      <p><strong>Name:</strong> {{ selectedUser.name }}</p>
      <p><strong>Email:</strong> {{ selectedUser.email }}</p>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      users: [
        { id: 1, name: 'John Doe', email: 'john@example.com' },
        { id: 2, name: 'Jane Doe', email: 'jane@example.com' },
        { id: 3, name: 'Alice Smith', email: 'alice@example.com' }
      ],
      selectedUser: null
    };
  },
  methods: {
    showDetails(user) {
      this.selectedUser = user;
    }
  }
});
</script>

<style scoped>
.user-table {
  width: 100%;
  border-collapse: collapse;
}

.user-table th, .user-table td {

  padding: 8px;
  border: 1px solid #ddd;
}

.user-table th {
  background-color: #f2f2f2;
  font-weight: bold;
  text-align: left;
}

.user-table tr:nth-child(even) {
  background-color: #f9f9f9;
}

.details {

  margin-top: 20px;
  padding: 10px;
  border: 1px solid #ccc;
}
</style>

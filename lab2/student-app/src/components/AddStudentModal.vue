<template>
  <div v-if="isOpen" class="modal">
    <div class="modal-content">
      <h3>Add New Student</h3>
      <label>ID:</label>
      <input v-model="newStudent.id" type="text" /><br />
      <label>Name:</label>
      <input v-model="newStudent.name" type="text" /><br />
      <label>City:</label>
      <input v-model="newStudent.city" type="text" /><br />
      <button @click="addStudent">OK</button>
      <button @click="$emit('close-modal')">Cancel</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["isOpen"],
  data() {
    return {
      newStudent: { id: "", name: "", city: "" },
    };
  },
  methods: {
    addStudent() {
      this.$emit("student-added", this.newStudent);
      this.newStudent = { id: "", name: "", city: "" }; 
    },
  },
};
</script>

<style>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}
.modal-content {
  background: white;
  padding: 20px;
  border-radius: 5px;
}
</style>

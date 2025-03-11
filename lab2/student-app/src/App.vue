<template>
  <div>
    <StudentsTable :students="students" @open-modal="isModalOpen = true" />
    <AddStudentModal 
      :isOpen="isModalOpen" 
      @student-added="addStudent"
      @close-modal="isModalOpen = false" 
    />
  </div>
</template>

<script>
import StudentsTable from "./components/StudentsTable.vue";
import AddStudentModal from "./components/AddStudentModal.vue";

export default {
  components: { StudentsTable, AddStudentModal },
  data() {
    return {
      students: [
        {id:100, name: "elshaar",city: "meet ghamr" },
        {id:200, name:"ahmed",city: "cairo" },
        {id:300, name: "mohamed",city: "alex" },
        {id:400, name:"moustafa", city:"mahala" },
      ],
      isModalOpen: false,
    };
  },
  methods: {
    addStudent(newStudent) {
      this.students.push(newStudent);
      this.isModalOpen = false;
    },
  },
};
</script>

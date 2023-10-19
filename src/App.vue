<template>
  <div id="app" class="app">
    <Form @tambah-tugas="tambahTugas" />
    <ListToDo :daftarTugas="daftarTugas" @hapus-tugas="hapusTugas" />
  </div>
</template>

<script>
import Form from "./components/Form.vue";
import ListToDo from "./components/ListToDo.vue";

export default {
  components: {
    Form,
    ListToDo,
  },
  data() {
    return {
      daftarTugas: [],
    };
  },
  methods: {
    tambahTugas(tugas) {
      this.daftarTugas.push(tugas);
    },
    hapusTugas(index) {
      this.daftarTugas.splice(index, 1);
    },
  },
};
</script>

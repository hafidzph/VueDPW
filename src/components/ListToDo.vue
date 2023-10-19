<template>
  <div class="list">
    <h1>LIST TO DO</h1>
    <ul>
      <li v-for="(tugas, index) in daftarTugas" :key="index">
        <h2>{{ tugas.nama }}</h2>
        <p>{{ tugas.deskripsi }}</p>
        <p>Hingga {{ tugas.tenggat }}</p>
        <p class="priority" :class="tugas.prioritas.toLowerCase()">
          {{ tugas.prioritas }}
        </p>
        <button @click="hapusTugas(index)">Hapus</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    daftarTugas: Array,
  },
  methods: {
    hapusTugas(index) {
      this.$emit("hapus-tugas", index);
    },
  },
};
</script>

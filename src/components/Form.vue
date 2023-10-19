<template>
  <div class="formToDo">
    <h1>To-Do List</h1>
    <form @submit.prevent="tambahTugas" class="form">
      <div class="input">
        <label for="nama">Tugas</label>
        <input
          type="text"
          id="nama"
          v-model="tugasBaru"
          placeholder="Tambah tugas..."
        />
      </div>
      <div class="input">
        <label for="deskripsi">Deskripsi</label>
        <input
          type="text"
          id="deskripsi"
          v-model="deskripsi"
          placeholder="Tambah deskripsi..."
        />
      </div>
      <div class="input">
        <label for="tenggat">Tenggat Waktu</label>
        <input type="date" id="tenggat" v-model="tenggat" />
      </div>
      <div class="input">
        <label for="prioritas">Prioritas</label>
        <select id="prioritas" v-model="prioritas">
          <option value="Tinggi">Tinggi</option>
          <option value="Sedang">Sedang</option>
          <option value="Rendah">Rendah</option>
        </select>
      </div>
      <button type="submit">Tambah</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tugasBaru: "",
      deskripsi: "",
      tenggat: "",
      prioritas: "Tinggi",
      daftarTugas: [],
    };
  },
  methods: {
    tambahTugas() {
      if (this.tugasBaru.trim() !== "") {
        this.$emit("tambah-tugas", {
          nama: this.tugasBaru,
          deskripsi: this.deskripsi,
          tenggat: this.tenggat,
          prioritas: this.prioritas,
        });
        this.tugasBaru = "";
        this.deskripsi = "";
        this.tenggat = "";
        this.prioritas = "Tinggi";
      }
    },
  },
};
</script>

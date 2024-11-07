<template>
  <div class="input-form">
    <input v-model="keterangan" placeholder="Keterangan" />
    <input v-model.number="jumlah" type="number" placeholder="Jumlah Uang" />
    <button @click="submitEntry">Submit</button>
  </div>
</template>

<script>
export default {
  name: "InputForm",
  data() {
    return {
      keterangan: "",
      jumlah: null
    };
  },
  methods: {
    submitEntry() {
      if (this.keterangan && this.jumlah) {
        this.$emit("add-entry", { keterangan: this.keterangan, jumlah: this.jumlah });
        this.keterangan = "";
        this.jumlah = null;
      }
    }
  }
};
</script>

<style scoped>
.input-form {
  display: flex;
  gap: 10px;
}
button {
  cursor: pointer;
}
</style>

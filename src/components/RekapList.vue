<template>
  <div class="list-section">
    <div v-for="(entry, index) in entries" :key="index" class="entry-item">
      <span>{{ entry.keterangan }}: Rp {{ entry.jumlah }}</span>
      <button @click="deleteEntry(index)">Hapus</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "RekapList",
  props: {
    entries: {
      type: Array,
      required: true
    }
  },
  methods: {
    deleteEntry(index) {
      this.$emit("delete-entry", index);
    }
  }
};
</script>

<style scoped>
.list-section {
  margin-top: 20px;
}
.entry-item {
  display: flex;
  justify-content: space-between;
  margin-bottom: 10px;
}
button {
  cursor: pointer;
}
</style>

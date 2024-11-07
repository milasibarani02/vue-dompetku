<template>
  <div class="dompetku">
    <h2>Dompetku – Expense & Income Management</h2>
    <InputForm @add-entry="addEntry" />
    <RekapList :entries="entries" @delete-entry="deleteEntry" />
    <button v-if="entries.length" @click="clearAll" class="clear-all">Hapus Semua</button>
  </div>
</template>

<script>
import InputForm from './components/InputForm.vue'
import RekapList from './components/RekapList.vue'

export default {
  name: 'DompetkuApp',
  components: {
    InputForm,
    RekapList,
  },
  data() {
    return {
      entries: [],
    }
  },
  methods: {
    addEntry(entry) {
      this.entries.push(entry)
    },
    deleteEntry(index) {
      this.entries.splice(index, 1)
    },
    clearAll() {
      this.entries = []
    },
  },
}
</script>

<style scoped>
.dompetku {
  max-width: 500px;
  margin: auto;
  text-align: center;
}
.clear-all {
  margin-top: 20px;
  padding: 10px;
  background-color: #f44336;
  color: white;
  border: none;
  cursor: pointer;
}
</style>

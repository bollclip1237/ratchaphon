<script setup>
const search = ref('')
const students = ref([
  { id: 1, name: 'Luminous Avanof', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 2, name: 'Luminous Javisz', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 3, name: 'Lauren S. Smith', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 4, name: 'Luminous Lopez', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 5, name: 'Alicia', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 6, name: 'Karina', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 7, name: 'Yasuo', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 8, name: 'Akari', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 9, name: 'Ahri', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 10, name: 'Arzir', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 11, name: 'Worwick', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 12, name: 'Zoe', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 13, name: 'Jhin', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 14, name: 'Kafta', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 15, name: 'Hertar', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 16, name: 'Zani', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 17, name: 'Cartethyia', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 18, name: 'Shorekeeper', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 19, name: 'Luno', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
  { id: 20, name: 'Carlotta', class: 'สทส.1/2', program: 'เทคโนโลยีสารสนเทศ' },
])
const filteredStudents = computed(() =>
  students.value.filter(student =>
    student.name.toLowerCase().includes(search.value.toLowerCase())
  )
)
</script>

<template>
  <div class="student-page">
    <h1 class="page-title">ข้อมูลนักเรียน</h1>

    <input
      v-model="search"
      type="text"
      placeholder="ค้นหาชื่อนักเรียน..."
      class="search-box"
    />

    <table class="student-table">
      <thead>
        <tr>
          <th>ลำดับ</th>
          <th>ชื่อ-นามสกุล</th>
          <th>ห้อง</th>
          <th>แผนการเรียน</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="student in filteredStudents" :key="student.id">
          <td>{{ student.id }}</td>
          <td>{{ student.name }}</td>
          <td>{{ student.class }}</td>
          <td>{{ student.program }}</td>

        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
.student-page {
  padding: 2rem;
  background-color: #111;
  color: white;
}

.page-title {
  font-size: 1.8rem;
  color: #3b82f6;
  margin-bottom: 1rem;
  text-align: center;
}

.search-box {
  width: 100%;
  max-width: 400px;
  padding: 0.75rem 1rem;
  margin: 0 auto 2rem;
  display: block;
  border-radius: 8px;
  border: none;
  background-color: #222;
  color: white;
  font-size: 1rem;
}

.search-box::placeholder {
  color: #888;
}

.student-table {
  width: 100%;
  border-collapse: collapse;
  background-color: #222;
  border-radius: 10px;
  overflow: hidden;
}

.student-table th,
.student-table td {
  padding: 1rem;
  border-bottom: 1px solid #333;
  text-align: left;
}

.student-table th {
  background-color: #333;
  color: #3b82f6;
}

.student-table tr:hover {
  background-color: #2a2a2a;
}
</style>

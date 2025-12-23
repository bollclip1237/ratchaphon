<script setup>
const staff = [
  {
    name: 'นายเชาวฤทธิ์ ลำพาย',
    position: 'ผู้อำนวยการ',
    photo: '/Images/ceo.jpg'
  },
  {
    name: 'นางสาวรัชญา คนธขจร',
    position: 'รองผู้อำนวยการ',
    photo: '/Images/sup ceo.jpg'
  },
  {
    name: 'นายสุระชัย วิเศษโวหาร',
    position: 'หัวหน้าแผนก',
    photo: '/Images/boss.jpg'
  },
  {
    name: 'นายนพพล อินศร',
    position: 'ครูประจำ',
    photo: '/Images/t1.jpg'
  },
  {
    name: 'ผ.ศ.สุธี เกินกลาง',
    position: 'ครูประจำ',
    photo: '/Images/t2.jpg'
  },
  {
    name: 'นางสาวสุภาดา คำตา',
    position: 'ครูประจำ',
    photo: '/Images/t3.jpg'
  },
  // เพิ่มบุคลากรตามต้องการ
]
</script>

<template>
  <div class="about-page">
    <h1 class="page-title">ข้อมูลบุคลากร</h1>
    <div class="staff-grid">
      <div v-for="person in staff" :key="person.name" class="staff-card">
        <img :src="person.photo" alt="staff photo" class="staff-img" height="280" />
        <h2 class="staff-name">{{ person.name }}</h2>
        <p class="staff-position">{{ person.position }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about-page {
  padding: 2rem;
  background-color: #111;
  color: white;
}

.page-title {
  font-size: 1.8rem;
  color: #3b82f6;
  margin-bottom: 2rem;
  text-align: center;
}

.staff-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* บรรทัดละ 3 คน */
  gap: 2rem;
}


.staff-card {
  background-color: #222;
  padding: 1.5rem;
  border-radius: 1rem;
  text-align: center;
  box-shadow: 0 0 10px rgba(0,0,0,0.5);
}

.staff-img {
  width: 100%;         /* ปรับให้เต็ม card */
  height: 660px;       /* ปรับความสูงตามต้องการ */
  object-fit: cover;   /* ตัดภาพให้พอดีกรอบแบบไม่เสียสัดส่วน */
  border-radius: 0.5rem;
  margin-bottom: 1rem;
}


.staff-name {
  font-size: 1.2rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
}

.staff-position {
  font-size: 0.95rem;
  color: #ccc;
}
</style>

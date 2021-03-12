<template>
  <div id="app">
    <div class="main__wrapper">
      <div class="main__left">
        <h1 style="margin-bottom: 20px">My Challanges</h1>
        <ul class="list-none">
          <li
            v-for="(challange, i) in challanges.default"
            :key="i"
          >
            <span>{{ challange.title }}</span>
            <button
              v-on:click="changeChallange(challange)"
              :disabled="challange.show"
            >
              Show Challange
            </button>
          </li>
        </ul>
      </div>
      <div class="main__right">
        <h1 style="margin-bottom: 20px">Clue Challanges</h1>
        <div v-if="challange === 0">
          <ul class="list-none">
            <li>
              <h3>Apa itu Vue ?</h3>
            </li>
            <li>
              Vue adalah kerangka kerja progresif untuk membangun antarmuka pengguna. Tidak seperti kerangka kerja monolitik lainnya, Vue dirancang dari awal agar dapat diadopsi secara bertahap. Pustaka inti difokuskan pada lapisan tampilan saja, dan mudah diambil dan diintegrasikan dengan pustaka lain atau proyek yang sudah ada. Di sisi lain, Vue juga sangat mampu mendukung Aplikasi Halaman Tunggal yang canggih
            </li>
            <li>
              <p style="margin-top: 20px">
                - Klik <i>Show Challange</i> untuk melihat tantangan
              </p>
            </li>
          </ul>
        </div>
        <div v-if="challange === 1">
          <ul class="list-none">
            <li>
              <h4>Prerequisite</h4>
            </li>
            <li>
              - Computed Properties and Watchers
            </li>
            <li>
              <h4>Task</h4>
            </li>
            <li>
              Buat Sebuah object data dengan nama "namaku" menggunakan camel case lalu buat sebuah fungsi dengan nama "hilangkanaku" menggunakan camel case pada properti computed, yang dimana fungsi ini menghilangkan huruf dominan yang ada pada object namaku.
            </li>
          </ul>
        </div>
        <div v-if="challange === 2">
          <ul class="list-none">
            <li>
              <h4>Prerequisite</h4>
            </li>
            <li>
              - Conditional Rendering
            </li>
            <li>
              <h4>Task</h4>
            </li>
            <li>
              Buat Sebuah object data dengan nama "active" lalu buat sebuah element div dan isi dengan "hello world!", jika kondisi active bernilai true maka element div tersebut muncul, sebaliknya jika bernilai false maka element div tersebut menghilang.  
            </li>
          </ul>
        </div>
        <div v-if="challange === 3">
          <ul class="list-none">
            <li>
              <h4>Prerequisite</h4>
            </li>
            <li>
              - List Rendering
            </li>
            <li>
              <h4>Task</h4>
            </li>
            <li>
              Buat Sebuah object data dengan nama "peoples" yang dimana object tersebut berisi sebuah "array object" dengan properti-properti ini "nama, umur, jenis_kelamin" lalu buat element "ul>li" yang dimana element tersebut menampilkan isi dari setiap data tersebut dengan format "nama - umur - jenis_kelamin" 
            </li>
          </ul>
        </div>
        <div v-if="challange === 4">
          <ul class="list-none">
            <li>
              <h4>Prerequisite</h4>
            </li>
            <li>
              - Component Registration
            </li>
            <li>
              <h4>Task</h4>
            </li>
            <li>
              Buat sebuah komponen lalu gunakan komponen tersebut di "halaman tertentu saja"
            </li>
          </ul>
        </div>
        <div v-if="challange === 5">
          <ul class="list-none">
            <li>
              <h4>Prerequisite</h4>
            </li>
            <li>
              - Props
            </li>
            <li>
              <h4>Task</h4>
            </li>
            <li>
              Buat sebuah komponen lalu tambahkan properti props dan tampilkan nilai dari props tersebut pada komponennya, gunakan komponen tersebut di "halaman tertentu saja" dan berikan sebuah nilai pada props tersebut melalui komponen atau halaman ini
            </li>
          </ul>
        </div>
        <div v-if="challange === 6">
          <ul class="list-none">
            <li>
              <h4>Prerequisite</h4>
            </li>
            <li>
              - Custom Events
            </li>
            <li>
              <h4>Task</h4>
            </li>
            <li>
              Buat sebuah komponen lalu buat sebuah 1 button pada komponen tersebut dan sebuah fungsi pada properti method yang dimana fungsi tersebut berjalan saat button di klik, keluarkan sebuah nilai saat button tersebut di klik dari parentnya dan tampung nilai tersebut pada sebuah data object parentnya
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      challanges: require('./assets/challanges'),
      challange: 0
    }
  },
  methods: {
    changeChallange(obj) {
      const newObj = this.challanges.default.find(data => data.id === obj.id)
      return this.challange = newObj.id
    }
  }
}
</script>

<style>
#app,
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: #2c3e50;
}
h3 {
  margin-bottom: 5px;
}
.main__wrapper {
  width: 100%;
  display: flex;
}
.main__left,
.main__right {
  padding: 10px;
}
.main__left {
  width: 50%;
  border: 1px solid #eee;
}
.main__right {
  width: 50%;
  border: 1px solid #eee;
}
.list-none {
  list-style: none;
}
.list-none li {
  padding: 5px 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.d-none {
  display: none;
}
.d-unset {
  display: unset;
}
</style>

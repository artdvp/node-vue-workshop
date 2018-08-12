<template>
  <div>
    <h1>Student List</h1>
    <v-select
          :items="clsList"
          v-model="cls"
          signle-line
          label="Filter"
          @change="getStudent"
    ></v-select>
    
    <select v-model="cls" @change="getStudent">
      <option value="1">1</option>
      <option value="2">2</option>
      <option value="3">3</option>
    </select>
    <ul>
      <li v-for="st in students" :key="st.id">
        {{ st.code }} - {{ st.fname }} - {{ st.lname }} - {{ st.class }}
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        cls: '1',
        students: [],
        clsList: [
            { value: '1', text: 'ชั้นปีที่ 1' },
            { value: '2', text: 'ชั้นปีที่ 2' },
            { value: '3', text: 'ชั้นปีที่ 3' },
        ]
      }
    },
    async created() {
      console.log('created')
      // 
      this.getStudent()
    },
    methods: {
      async getStudent() {
        // let res = await this.$http.get(`/student?class=${this.cls}`)
        let res = await this.$http.get('/student', { params: { class: this.cls}})
        console.log(res.data)
        this.students = res.data.student
      }
    }
  }

</script>

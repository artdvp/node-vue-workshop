<template>
    <div class="con-center">
        <h1>02. v-model</h1>
        <br><hr>
        <h1>Hello {{ name }}</h1>
        <input type="text" :value="name"/>
        <br><br>
        <input type="text" v-model="name"/>
    </div>
</template>

<script>
export default {
  data() {
    // ใช้ arrow function เพื่อป้อง this ซ้ำซ้อน
    // setInterval(() => {
    //   this.name += "*";
    // }, 3000);

    return {
      name: "Artdvp"
    };
  }
};
</script>

<style>
.con-center {
  text-align: center;
  margin-top: 1rem;
}
</style>
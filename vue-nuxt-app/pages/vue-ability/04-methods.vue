<template>
    <div class="con-center">
        <h1>04. methods</h1>
        <br><hr>
        <h1>Hello {{ name }}</h1>
        <h2>UP NAME - {{ upperName }}</h2>
        <br>
        <input type="text" :value="name"/>
        <br><br>
        <input type="text" v-model="name"/>
        <br><br>
        <v-btn @click="doSave">
          <v-icon dark>favorite</v-icon>
          Save
        </v-btn>
    </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Artdvp"
    };
  },
  computed: {
    upperName() {
      return this.name.toUpperCase();
    }
  },
  methods: {
    doSave() {
      console.log("This is name : " + this.name);
    }
  }
};
</script>

<style>
.con-center {
  text-align: center;
  margin-top: 1rem;
}
</style>
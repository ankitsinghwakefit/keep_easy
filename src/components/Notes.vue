<template>
  <div class="body">
    <input 
    placeholder="Take a note..." 
    class="input-box" 
    v-model="newNote"
    @keypress.enter="saveNote"
    />
  </div>
</template>

<script>
export default {
  name: "Notes",
  data() {
    return {
      newNote: "",
      allNotes: [],
    };
  },
  methods: {
    saveNote(){
      alert('hii')
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.body {
  width: 60%;
  margin: 60px auto;
}
.input-box {
  width: 600px;
  box-shadow: 0 1px 2px 0 rgba(60, 64, 67, 0.302),
    0 2px 6px 2px rgba(60, 64, 67, 0.149);
  border-radius: 8px;
  color: #202124;
  height: 46px;
  background-color: #fff;
  border-color: #e0e0e0;
  border: 1px solid transparent;
  font-size: 18px;
  padding: 5px 10px;
}
input:focus,
select:focus {
  outline: none;
  color: #202124;
}
</style>

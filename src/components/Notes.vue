<template>
  <div class="body">
    <input 
    placeholder="Take a note..." 
    class="input-box" 
    v-model="newNote"
    @keypress.enter="saveNote"
    />
    <div class="notes-item">
      <div>
        some notese here
      </div>
      <div class="remove-icon">
        &times;
      </div>
    </div>
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
  max-width: 600px;
  margin: 60px auto;
}
.input-box {
  width: 100%;
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
.notes-item {
  width: 100%;
  border: solid transparent;
  border-width: 0 0 0 4px;
  color: #202124;
  margin-top: 30px;
  font-size: 16px;
  margin-bottom: 12px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 6px 10px;
  box-shadow: none;
  opacity: 1;
  border-radius: 8px;
  background-color: #fff;
  border: 1px solid #e0e0e0;
  min-height: 16px;
}
.remove-icon {
  cursor: pointer;
  margin-left: 14px;
}
</style>

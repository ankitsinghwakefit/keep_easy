<template>
  <div class="body">
    <div class="instruction-screen" v-if="toggle">
      <h3>
        Instructions : How to use our Notepad to keep all your notes at a place.
      </h3>
      <ul>
        <li>Type new note in Input box.</li>
        <li>Done! Press enter to save.</li>
        <li>Want to update note? Double click on note to edit.</li>
        <li>Yes!!! yon can delete note by clicking on X</li>
      </ul>
      <button @click="toggleScreen" class="btn">Let's Try!</button>
    </div>
    <div v-if="!toggle" class="Notepad">
      <h3>Keep Notes...</h3>
      <input
        placeholder="Take a note..."
        class="input-box"
        v-model="newNote"
        @keypress.enter="saveNote"
      />
      <div v-for="(note, index) in allNotes" :key="index" class="notes-item">
        <div class="note-bar-wrapper">
          <div
            v-if="!note.edit"
            @dblclick="editNote(note)"
            class="notes-data-bar"
          >
            {{ note.body }}
          </div>
          <input
            v-else
            class="notes-editor"
            @blur="doneEdit(note)"
            @keypress.enter="doneEdit(note)"
            v-model="note.body"
          />
        </div>
        <div @click="deleteNote(index)" class="remove-icon">
          &times;
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Notes",
  data() {
    return {
      toggle: true,
      newNote: "",
      allNotes: [],
    };
  },
  methods: {
    saveNote() {
      this.allNotes.push({
        body: this.newNote,
        edit: false,
      });
      this.newNote = "";
    },
    deleteNote(index) {
      this.allNotes.splice(index, 1);
    },
    editNote(data) {
      data.edit = true;
    },
    doneEdit(newData) {
      newData.edit = false;
    },
    toggleScreen() {
      this.toggle = false;
    },
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
  min-height: 34px;
  overflow: hidden;
}
.remove-icon {
  cursor: pointer;
  margin-left: 14px;
}
.note-bar-wrapper {
  display: flex;
  align-items: center;
}
.notes-editor {
  border: none;
  font-size: 16px;
}
.notes-editor:focus {
  outline: none;
  color: #202124;
  font-size: 16px;
}
.notes-notes-data-bar {
  letter-spacing: 0.01428571em;
  font-family: Helvetica;
  font-size: 0.875rem;
  font-weight: 400;
  line-height: 1.25rem;
}
.Instruction {
  margin-top: 300px;
}
.instruction-screen {
  text-align: left;
}
.btn {
  margin-top: 30px;
  width: 100px;
  height: 35px;
  font-size: 18px;
  border-radius: 17px;
}
</style>

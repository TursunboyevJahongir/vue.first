<template>
  <div class="new-note">
    <input type="text" class="form-control" v-model="note.title" />
    <br>
    <textarea class="form-control" v-model="note.description" rows="3"></textarea>
    <button class="btn btn-outline-success" @click="addNote">Add New note</button>
  </div>
</template>

<script>
export default {
  props: {
    note: {
      type: Object,
      requare: true,
    },
  },
  methods: {
    addNote() {
      this.$emit("addNote", this.note);
    },
  },
};
</script>

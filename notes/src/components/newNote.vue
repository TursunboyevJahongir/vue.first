<template>
  <div class="new-note">
    <input type="text" v-model="note.title" />
    <textarea v-model="note.description"></textarea>
    <button class="btn btn-secondary" @click="addNote">note</button>
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

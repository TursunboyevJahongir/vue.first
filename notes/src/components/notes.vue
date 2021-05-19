<template>
  <div class="notes">
    <div class="note" v-for="(note, index) in notes" :key="index">
      <div class="row">
        <div class="note-header col-12 col-md-5">
          <p>{{ note.title }}</p>
        </div>
        <div class="col-12 col-md-3">
          <button @click="removeNote(index)">Delete</button>
        </div>
      </div>
      <div class="note-body col-6 col-md-6">
        <p>{{ note.description }}</p>
        <span>{{ note.date }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    notes: {
      type: Array,
      requare: true,
    },
  },
  methods: {
    removeNote(index){
      console.log(`id ${index}`)
      this.$emit('remove',index)
    }
  },
};
</script>
<style>
.notes {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  padding: 40px 0;
}
.note {
  width: 48%;
  padding: 18px 20px;
  margin-bottom: 20px;
  background-color: #fff;
}
.note-header {
  color: red;
}
.note-body {
  border: 1px solid rgba(71, 115, 172, 0.438);
  margin: 20px 0;

  font-size: 14;
  color: rgb(61, 60, 60);
}
</style>

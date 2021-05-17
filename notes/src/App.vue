<template>
  <div class="wrapper">
    <div class="wrapper-content">
      <section>
        <div class="container">
          {{ title }}

          <!-- <message v-if='message' :message="this.message">
      </message> -->
          <message v-if="message" :message="this.message" />
          <newNote :note="note" @addNote="addNote" />

          <div class="notes">
            <div v-for="(note, index) in notes" :key="index">
              <div class="note-header">
                <p>{{ note.title }}</p>
              </div>
              <div class="note-body">
                <p>{{ note.description }}</p>
                <span>{{ note.date }}</span>
              </div>
              <hr />
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import message from "@/components/Messages.vue";
import newNote from "@/components/newNote.vue";
// import message from './components/Messages.vue';

export default {
  components: {
    message,
    newNote,
  },
  data() {
    return {
      title: "hi",
      note: {
        title: "",
        description: "",
        message: null,
      },
      notes: [
        {
          title: "first",
          description: "loremAliquip quis adipisicing magna laboris.",
          date: new Date(Date.now()).toLocaleString(),
        },
        {
          title: "second",
          description:
            "Cupidatat ex anim ea anim. Ipsum laboris amet ad nisi irure occaecat consequat occaecat mollit magna sit. Consequat deserunt officia et dolore cillum ipsum dolor incididunt laborum laboris. Excepteur magna mollit irure anim est irure dolore consequat irure officia reprehenderit. Exercitation id labore minim do in.",
          date: new Date(Date.now()).toLocaleString(),
        },
        {
          title: "third",
          description:
            "Irure velit et aute minim ad eiusmod nulla officia deserunt dolore aliqua ut cupidatat. Magna minim duis minim consectetur officia laborum eu aliqua consectetur quis consequat. Elit voluptate amet ullamco consequat culpa Lorem deserunt magna excepteur fugiat. Amet ipsum est deserunt est sit mollit deserunt.",
          date: new Date(Date.now()).toLocaleString(),
        },
      ],
    };
  },
  methods: {
    addNote() {
      let { title, description } = this.note;
      if (title === "") {
        this.message = "title can't blanck";
        // alert("title can't blanck");
        return false;
      }
      this.message = null;
      this.notes.push({
        title,
        description,
        date: new Date(Date.now()).toLocaleString(),
      });
      this.note.title = "";
      this.note.description = "";
    },
  },
};
</script>

<style></style>

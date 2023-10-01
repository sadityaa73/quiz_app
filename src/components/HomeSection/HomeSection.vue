<template>
  <div id="home">
    <div class="container-one">
      <div class="subjects-container" v-for="(subject,id) in subjects" :key="id">
        <div class="subject-image">
          <img
            :src="subject.imgSrc"
            :alt="subject.subjectName"
            style="
              width: 310px;
              height: 180px;
              margin-left: auto;
              margin-right: auto;
            "
          />
        </div>
        <div class="start-btn" @click="startQuiz(subject.subjectName)">
          start quiz
        </div>
      </div>
    </div>
    <div class="container-two">
      <div class="incoming-events">
        <div class="heading">Upcoming Event</div>
        <div class="event-info">
          <ul class="event-list" v-for="(event,id) in upCommingEvents" :key="id">
            <li>{{ event.eventName }}</li>
          </ul>
        </div>
      </div>
      <div class="statstics">
        <div class="heading">Statistic</div>
        <div style="height: 220px; width: auto; overflow: hidden">
          <canvas id="acquisitions"></canvas>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Chart from "chart.js/auto";
export default {
  components: {},
  emits: ["subjectName", "isStart"],
  data() {
    return {
      subjects: [
        {
          id: 1,
          subjectName: "physics",
          imgSrc:
            "https://www.environmentalscience.org/wp-content/uploads/2018/08/physics-300x300.webp",
        },
        {
          id: 2,
          subjectName: "chemistry",
          imgSrc:
            "https://www.thoughtco.com/thmb/bcj-0Qw8kGp6JQPryxb6vrr5Cc4=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc():format(webp)/GettyImages-545286316-433dd345105e4c6ebe4cdd8d2317fdaa.jpg",
        },
        {
          id: 1,
          subjectName: "computerScience",
          imgSrc:
            "https://blogassets.leverageedu.com/blog/wp-content/uploads/2020/06/22210327/BE-Computer-Science.png",
        },
      ],
      upCommingEvents: [{ id: 1, eventName: "New Quiz are comming up!!" }],
    };
  },
  mounted() {
    this.getGraph();
  },
  methods: {
    async getGraph() {
      const data = [
        { subject: "physics", count: 0 },
        { subject: "checmistry", count: 0 },
        { subject: "computer science", count: 0 },
      ];
      await new Chart(document.getElementById("acquisitions"), {
        type: "bar",
        data: {
          labels: data.map((row) => row.subject),
          datasets: [
            {
              label: "Acquisitions by subjects",
              data: data.map((row) => row.count),
            },
          ],
        },
      });
    },
    startQuiz(subject) {
      console.log("printing argument", subject);
      this.$emit("subjectName", { subject: subject, isStart: true });
    },
  },
};
</script>
<style scoped>
#home {
  min-width: 70%;
  min-height: 49vh;
  border-radius: 9px;
  box-shadow: 1px 3px 8px 3px grey;
  margin: 1%;
}
.container-one {
  display: flex;
}
.subjects-container {
  border: 1px solid;
  min-width: 20%;
  min-height: 17vh;
  margin: 3%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 9px;
  background: white;
}
.subject-image {
  border: 1px solid;
  min-height: 12vh;
  margin: 7%;
  width: 80%;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
}
.start-btn {
  position: relative;
  margin: 7%;
  font-size: 20px;
  font-family: cursive;
  border: 1px solid;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 52%;
  min-height: 30px;
  border-radius: 7px;
  color: white;
  background: dodgerblue;
  top: 0px;
  overflow: hidden;
}
.start-btn:hover {
  box-shadow: 1px 3px 8px 3px grey;
}
.start-btn:active {
  background: yellowgreen;
  color: black;
}
.container-two {
  display: flex;
}
.incoming-events {
  border: 1px solid;
  min-width: 40%;
  min-height: 40vh;
  margin: 3%;
  border-radius: 9px;
  background: white;
}
.statstics {
  border: 1px solid;
  min-width: 48%;
  min-height: 40vh;
  margin: 3%;
  border-radius: 9px;
  background: white;
}
.heading {
  border: 1px solid;
  position: relative;
  min-height: 17%;
  border-radius: 9px 9px 0px 0px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #2a8ff7;
  color: white;
  font-size: 20px;
  font-family: cursive;
  overflow: hidden;
}
.event-info {
  margin: 3%;
  min-height: 75%;
  max-height: 75%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  overflow: auto;
}
.event-list {
  box-shadow: 1px 1px 5px 3px lightgray;
  list-style: none;
  margin: 2%;
  min-height: 30px;
  border-radius: 7px;
  padding: 0px;
  display: flex;
  align-items: center;
}
li {
  margin-left: 1%;
}
</style>

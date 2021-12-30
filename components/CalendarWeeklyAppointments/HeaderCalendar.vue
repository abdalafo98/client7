<template>
  <div>
    <div class="son" v-if="getLanguage === 'ar'">
      <ArrowHeaderLeft @increase-date="increaseDate" />
      <WeekFromTo />
      <h2 class="week-from-to">
        <ArrowHeaderRight @decrease-date="decreaseDate" />
      </h2>
    </div>
    <div v-else class="son">
      <ArrowHeaderRight @decrease-date="decreaseDate" />

      <h2 class="week-from-to">
        <WeekFromTo />
      </h2>
      <ArrowHeaderLeft @increase-date="increaseDate" />
    </div>
  </div>
</template>

<script>
import ArrowHeaderRight from "./ArrowHeaderRight.vue";
import ArrowHeaderLeft from "./ArrowHeaderLeft.vue";
import WeekFromTo from "./WeekFromTo.vue";
export default {
  components: { ArrowHeaderRight, ArrowHeaderLeft, WeekFromTo },

  computed: {
    getLanguage() {
      return this.$store.getters.getLanguage;
    },
  },

  methods: {
    decreaseDate() {
      this.$store.dispatch("addDays", {
        date: this.$store.getters.getStartDate,
        num: -7,
        status: "change_startDate",
      });
      if (this.$route.name === "weeklyappointments") {
        this.$store.dispatch("getAppoinments");
        this.$store.dispatch("getFilters");
      } else if (this.$route.name === "weeklyCalendarById") {
        this.$store.dispatch("getWeeklyAppointmentById");
        this.$store.dispatch("getFilters");
      }
    },
    increaseDate() {
      this.$store.dispatch("addDays", {
        date: this.$store.getters.getStartDate,
        num: 7,
        status: "change_startDate",
      });
      if (this.$route.name === "weeklyappointments") {
        this.$store.dispatch("getAppoinments");
        this.$store.dispatch("getFilters");
      } else if (this.$route.name === "weeklyCalendarById") {
        this.$store.dispatch("getWeeklyAppointmentById");
        this.$store.dispatch("getFilters");
      }
    },
  },
};
</script>

<style scoped>
.son {
  margin-left: 15px;
  display: flex;
  justify-content: right;
  flex-wrap: wrap;
  grid-gap: 10px;
  gap: 10px;
  margin-right: 15px;
}
.week-from-to {
  color: #949191;
  font-size: 18px;
  font-weight: 100;
}
</style>

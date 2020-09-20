<template>
  <div class="date-display mt-3">
    <div class="date small mb-2 border mr-3 ml-3">
      <span>
        <CalendarIcon class="text-primary mr-3" />
        <time datetime="2020-10-07">7 Oct, Weds</time>
      </span>
      <span>
        <ClockIcon class="text-primary mr-3" />
        <time datetime="10:15+2:00">10:15AM - 10:30AM</time>
      </span>
    </div>
    <CustomText muted>Timezone: Europe/Amsterdam</CustomText>
  </div>
</template>
<script>
import CalendarIcon from "../icons/calendar.svg";
import ClockIcon from "../icons/clock.svg";
import CustomText from "./CustomText";

export default {
  name: "DateDisplay",
  components: {
    CalendarIcon,
    ClockIcon,
    CustomText
  },
  data: function() {
    return {
      date: {
        type: String
      },
      time: {
        type: String
      }
    };
  }
};
</script>
<style scoped>
.date-display {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.date {
  display: flex;
  align-items: center;
  padding: 15px 5px;
  max-width: 300px;
}
.date span {
  display: flex;
  align-items: center;
  margin: 0 10px;
}
</style>

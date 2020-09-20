<template>
  <div class="date-display">
    <div class="date small border">
      <span>
        <CalendarIcon class="text-primary" />
        <time datetime="2020-10-07">7 Oct, Weds</time>
      </span>
      <span>
        <ClockIcon class="text-primary" />
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
  props: {
    datetime: {
      type: String
    }
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
  margin-top: 15px;
  margin-bottom: 8px;
  max-width: 300px;
}
.date span {
  display: flex;
  align-items: center;
  margin: 0 10px;
}
.date span svg {
  margin-right: 10px;
}
</style>

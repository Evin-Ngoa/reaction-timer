<template>
  <p>Reaction time: {{ score }} ms</p>
  <p class="rank" :class="{'gold' : score < 250}">
      {{ rank }}
    </p>
</template>

<script>
export default {
  
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "Gold [1] : Ninja Fingers";
    } else if (this.score < 400) {
      this.rank = "Silver [2] : Fast Reflexes";
    } else {
      this.rank = "Bronze [3] : Too Slow :(";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4em;
  color: #1478be;
  font-weight: bold;
}
.rank.gold {
  color: #ffd700;
}
</style>
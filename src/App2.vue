<!-- Leaderboard.vue -->

<script setup>
import { ref, computed } from "vue";

// Constants
const CROWN_COLORS = ["#FB9639", "#00D95F", "#009BD6"];
const IMAGE_PATH = "../public/";

const leaderboardData1 = ref([
  { name: "John", score: 2457, username: "@johnjacob23" },
  { name: "Alice", score: 1893, username: "@alice_wonder" },
  { name: "Bob", score: 3025, username: "@bob_the_builder" },
  { name: "Eva", score: 1500, username: "@eva_adventurer" },
  { name: "Charlie", score: 2201, username: "@charlie_coder" },
  { name: "Grace", score: 1987, username: "@grace_innovator" },
  { name: "David", score: 2754, username: "@david_developer" },
  { name: "Sophie", score: 1923, username: "@sophie_artist" },
  { name: "Michael", score: 3120, username: "@michael_musician" },
  { name: "Olivia", score: 2345, username: "@olivia_bookworm" },
  { name: "James", score: 2678, username: "@james_gamer" },
  { name: "Emma", score: 2056, username: "@emma_explorer" },
  { name: "William", score: 2901, username: "@william_wanderer" },
  { name: "Ava", score: 1789, username: "@ava_architect" },
  { name: "Daniel", score: 2603, username: "@daniel_dreamer" },
  { name: "Mia", score: 2134, username: "@mia_mediator" },
  { name: "Jackson", score: 3302, username: "@jackson_joker" },
  { name: "Sophia", score: 1956, username: "@sophia_scientist" },
  { name: "Liam", score: 2809, username: "@liam_linguist" },
  { name: "Isabella", score: 2245, username: "@isabella_idealist" },
]);

const leaderboardData = computed(() =>
  leaderboardData1.value.slice().sort((a, b) => b.score - a.score)
);
</script>

<template>
  <div class="leaderboard-container">
    <!-- Header Section -->
    <div class="header-section">
      <h1 class="leaderboard-title text-3xl font-bold text-white">
        Top Contributors
      </h1>
    </div>

    <!-- Top Contributors Section -->
    <div class="top-contributors-section">
      <!-- Contributor Card (1st place) -->
      <div class="contributor-card gold">
        <div class="crown">
          <img src="../public/gold-crown.jpeg" alt="Gold Crown" />
        </div>
        <div class="profile-pic gold">
          <img src="../public/first.jpeg" alt="Profile Pic" />
        </div>
        <div class="contributor-info">
          <span class="name text-white">{{ leaderboardData[0].name }}</span>
          <span class="score text-[#FB9639]">{{
            leaderboardData[0].score
          }}</span>
          <span class="username text-white text-xs">{{
            leaderboardData[0].username
          }}</span>
        </div>
      </div>

      <!-- Contributor Card (2nd place) -->
      <div class="contributor-card silver">
        <div class="crown">
          <img src="../public/silver-crown.jpg" alt="Silver Crown" />
        </div>
        <div class="profile-pic silver">
          <img src="../public/second.jpeg" alt="Profile Pic" />
        </div>
        <div class="contributor-info">
          <span class="name text-white">{{ leaderboardData[1].name }}</span>
          <span class="score text-[#00D95F]">{{
            leaderboardData[1].score
          }}</span>
          <span class="username text-white text-xs">{{
            leaderboardData[1].username
          }}</span>
        </div>
      </div>

      <!-- Contributor Card (3rd place) -->
      <div class="contributor-card bronze">
        <div class="crown">
          <img src="../public/bronze-crown.jpg" alt="Bronze Crown" />
        </div>
        <div class="profile-pic bronze">
          <img src="../public/third.jpeg" alt="Profile Pic" />
        </div>
        <div class="contributor-info">
          <span class="name text-white">{{ leaderboardData[2].name }}</span>
          <span class="score text-[#009BD6]">{{
            leaderboardData[2].score
          }}</span>
          <span class="username text-white text-xs">{{
            leaderboardData[2].username
          }}</span>
        </div>
      </div>
    </div>

    <!-- Other Contributors Section -->
    <div class="other-contributors-section">
      <ul class="contributor-list">
        <li
          v-for="(item, index) in leaderboardData"
          :key="index"
          class="contributor-item"
        >
          <div class="ranking">
            <span class="text-white">{{ index + 4 }}</span>
          </div>
          <div class="profile-pic">
            <img :src="`${IMAGE_PATH}fourth.jpeg`" alt="Profile Pic" />
          </div>
          <div class="contributor-info">
            <span class="text-white">{{ item.name }}</span>
            <span class="text-white text-xs">{{ item.username }}</span>
          </div>
          <div class="score">
            <span class="text-white">{{ item.score }}</span>
          </div>
          <div class="divider-line"></div>
        </li>
      </ul>
    </div>
  </div>
</template>

<style lang="scss" scoped>
/* Common Styles */
.leaderboard-container {
  @apply w-screen h-screen flex justify-center items-center;
  background-color: #d2d3da;
}

/* Header Section Styles */
.header-section {
  @apply w-full h-[10%] flex justify-center items-center;
}

/* Top Contributors Section Styles */
.top-contributors-section {
  @apply h-[30%] w-full flex justify-center items-center;
}

/* Contributor Card Styles */
.contributor-card {
  @apply w-[30%] h-full flex justify-center items-end;
  position: relative;

  &.gold {
    @apply bg-[#252A40];
  }

  &.silver {
    @apply bg-[#1E2237];
  }

  &.bronze {
    @apply bg-[#1E2237];
  }

  .crown {
    @apply absolute -top-[40%] w-[70px] h-[70px] bg-black rounded-full;
    img {
      @apply relative w-full h-full rounded-full;
    }
  }

  .profile-pic {
    @apply w-[25%] h-full flex justify-center items-center;
    img {
      @apply w-[55px] h-[55px] rounded-full;
    }
  }

  .contributor-info {
    @apply w-[75%] h-full flex justify-between items-center p-2;
  }

  .name {
    @apply text-white;
  }

  .score {
    @apply text-[#FB9639];
  }

  .username {
    @apply text-white text-xs;
  }
}

/* Other Contributors Section Styles */
.other-contributors-section {
  @apply h-[60%] w-full flex justify-center pt-2 items-center;
}

/* Contributor List Styles */
.contributor-list {
  @apply w-full h-full p-1 rounded-t-3xl bg-[#1E2237] space-y-2 overflow-y-auto;
}

/* Contributor Item Styles */
.contributor-item {
  @apply w-full h-[70px] m-0 flex flex-col items-center space-y-[10px];

  .ranking {
    @apply h-full flex justify-center items-center pl-2;
  }

  .profile-pic {
    @apply w-[25%] h-full flex justify-center items-center;
    img {
      @apply w-[55px] h-[55px] rounded-full;
    }
  }

  .contributor-info {
    @apply w-[75%] h-full flex justify-between items-center p-2;
  }

  .score {
    @apply text-white;
  }

  .divider-line {
    @apply h-[1px] w-[70%] bg-[#5F5959];
  }
}
</style>

<script setup>
import { ref, computed } from "vue";

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

// Create a computed property for the sorted data
const leaderboardData = computed(() =>
  leaderboardData1.value.slice().sort((a, b) => b.score - a.score)
);
</script>
<template>
  <div class="w-screen h-screen bg-[#D2D3DA] flex justify-center items-center">
    <div
      class="max-w-[800px] max-h-[700px] rounded-lg w-full h-full -2 bg-[#151729]"
    >
      <div class="w-full h-[10%] flex justify-center items-center">
        <h1 class="text-3xl font-bold text-white">Top Contributors</h1>
      </div>
      <div class="h-[30%] w-full flex justify-center items-center">
        <div class="w-[80%] h-[90%] flex">
          <div class="h-full flex justify-center items-end w-[30%]">
            <div
              class="w-full h-[60%] rounded-tl-xl flex-col relative flex justify-center items-center bg-[#1E2237]"
            >
              <div
                class="absolute -top-[40%] w-[70px] h-[70px] bg-black rounded-full"
              >
                <div class="relative w-full h-full rounded-full">
                  <img
                    class="w-full h-full rounded-full"
                    src="../public/second.jpeg"
                  />
                  <div
                    class="-top-7 -right-5 absolute w-10 h-10 rotate-45 bg-green-400 border-2 border-white dark:border-gray-800 rounded-full"
                  >
                    <img
                      class="w-full h-full rounded-full"
                      src="../public/silver-crown.jpg"
                    />
                  </div>
                </div>
              </div>
              <span class="text-white">{{ leaderboardData[0].name }}</span>
              <span class="text-[#00D95F]">{{ leaderboardData[1].score }}</span>
              <span class="text-white text-xs">{{
                leaderboardData[0].username
              }}</span>
            </div>
          </div>
          <div class="h-full flex justify-center items-end w-[40%]">
            <div
              class="w-full h-[70%] rounded-t-xl flex-col bg-[#252A40] relative flex justify-center items-center"
            >
              <div
                class="absolute -top-[40%] w-[70px] h-[70px] bg-black rounded-full"
              >
                <div class="relative w-full h-full rounded-full">
                  <img
                    class="w-full h-full rounded-full"
                    src="../public/first.jpeg"
                  />
                  <div
                    class="-top-7 -right-5 absolute w-10 h-10 rotate-45 bg-green-400 border-2 border-white dark:border-gray-800 rounded-full"
                  >
                    <img
                      class="w-full h-full rounded-full"
                      src="../public/gold-crown.jpeg"
                    />
                  </div>
                </div>
              </div>
              <span class="text-white">{{ leaderboardData[1].name }}</span>
              <span class="text-[#FB9639]">{{ leaderboardData[0].score }}</span>
              <span class="text-white text-xs">{{
                leaderboardData[1].username
              }}</span>
            </div>
          </div>
          <div class="h-full flex justify-center items-end w-[30%]">
            <div
              class="w-full h-[60%] rounded-tr-xl flex-col bg-black/20 relative flex justify-center items-center bg-[#1E2237]"
            >
              <div
                class="absolute -top-[40%] w-[70px] h-[70px] bg-black rounded-full"
              >
                <div class="relative w-full h-full rounded-full">
                  <img
                    class="w-full h-full rounded-full"
                    src="../public/third.jpeg"
                  />
                  <div
                    class="-top-7 -right-5 absolute w-10 h-10 rotate-45 bg-green-400 border-2 border-white dark:border-gray-800 rounded-full"
                  >
                    <img
                      class="w-full h-full rounded-full"
                      src="../public/bronze-crown.jpg"
                    />
                  </div>
                </div>
              </div>
              <span class="text-white">{{ leaderboardData[3].name }}</span>
              <span class="text-[#009BD6]">{{ leaderboardData[2].score }}</span>
              <span class="text-white text-xs">{{
                leaderboardData[3].username
              }}</span>
            </div>
          </div>
        </div>
      </div>
      <div class="h-[60%] w-full flex justify-center pt-2 items-center">
        <li
          class="w-full h-full p-1 rounded-t-3xl bg-[#1E2237] space-y-2 overflow-y-auto"
        >
          <ul
            v-for="(item, index) in leaderboardData"
            class="w-full h-[70px] m-0 flex flex-col items-center space-y-[10px]"
          >
            <div class="w-full h-[55px] flex">
              <div class="h-full flex justify-center items-center pl-2">
                <span class="text-white">{{ index + 1 }}</span>
              </div>
              <div class="w-[25%] h-full flex justify-center items-center">
                <div class="w-[55px] h-[55px] rounded-full">
                  <img
                    class="w-full h-full rounded-full"
                    src="../public/fourth.jpeg"
                  />
                </div>
              </div>
              <div class="w-[75%] h-full flex justify-between items-center p-2">
                <div class="flex flex-col">
                  <span class="text-white">{{ item.name }}</span>
                  <span class="text-white text-xs">{{ item.username }}</span>
                </div>
                <div class="">
                  <span class="text-white">{{ item.score }}</span>
                </div>
              </div>
            </div>
            <div class="h-[1px] w-[70%] bg-[#5F5959]"></div>
          </ul>
        </li>
      </div>
    </div>
  </div>
</template>

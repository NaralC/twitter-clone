<script setup lang="ts">
const whatsHappeningItems = ref([
  {
    title: "SpaceX",
    count: "18.8k Tweets",
  },
  {
    title: "Obama",
    count: "200k Tweets",
  },
  {
    title: "Titanfall",
    count: "8k Tweets",
  },
]);

const whoToFollowItems = ref([
  {
    name: "Joe Biden",
    handle: "@JoeBidenOfficialLmao",
    image: "https://picsum.photos/200/200",
  },
  {
    name: "Barack Obama",
    handle: "@YourLoadAndSaviorObama",
    image: "https://picsum.photos/200/200",
  },
]);
</script>

<template>
  <div class="flex flex-col">
    <!-- Preview card: what's happening -->
    <SidebarRightPreviewCard title="What's Happening">
      <SidebarRightPreviewCardItem v-for="item in whatsHappeningItems">
        <div>
          <h2 class="text-base font-bold text-gray-800 dark:text-white">
            {{ item.title }}
          </h2>
          <p class="text-xs text-gray-400">
            {{ item.count }}
          </p>
        </div>
      </SidebarRightPreviewCardItem>
    </SidebarRightPreviewCard>

    <!-- Preview card: who to follow -->
    <SidebarRightPreviewCard title="Who to Follow">
      <SidebarRightPreviewCardItem v-for="item in whoToFollowItems">
        <div class="flex flex-row justify-between p-2">
          <div class="flex flex-row">
            <img
              class="w-10 h-10 rounded-full"
              :src="item.image"
              :alt="item.name"
            />

            <div class="flex flex-col ml-2">
              <h1 class="text-sm font-bold text-gray-900 dark:text-white">
                {{ item.name }}
              </h1>
              <p class="text-xs text-gray-400 truncate">{{ item.handle }}</p>
            </div>
          </div>
          <div class="flex h-full">
            <button
              class="px-4 py-2 text-xs font-bold text-white bg-black rounded-full dark:bg-white dark:text-black"
            >
              Follow
            </button>
          </div>
        </div>
      </SidebarRightPreviewCardItem>
    </SidebarRightPreviewCard>
  </div>
</template>

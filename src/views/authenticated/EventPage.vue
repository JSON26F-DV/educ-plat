<template>
  <NavigationBar></NavigationBar>
   <div class="Foryoupage container-fluid w-screen h-screen flex_centered flex-row! gap-5 mt-20 px-5">
      <!-- Left Navigation Sidebar -->
      <div
        class="h-[768px] self-start whitespace-nowrap overflow-x-hidden overflow-y-auto scrollbar scrollbar-thumb-gray-300 "
      >
        <SideBar></SideBar>
      </div>
      <!-- Main Content: Communities list -->
      <main class="flex-[2.5] flex_full flex_centered justify-start gap-5">
        <h2 class="text-2xl font-bold mb-4">Exclusive Events</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <!-- Community card template repeated for multiple communities -->
          <CommunityOutput
            v-for="(event, index) in events"
            :key="index"
            :event="event"
          />


        </div>
        <!-- Create Community CTA -->
      </main>
    </div>
</template>

<script setup>
import NavigationBar from '@/components/NavigationBar.vue';
import SideBar from '@/components/SideBar.vue';
import CommunityOutput from '@/components/CommunityOutput.vue';

const events = [
  {
    logo: '🎉',
    title: 'Battle of the Bands',
    content: 'Join us for weekly jam sessions and collaborative music-making.'
  },
  {
    logo: '💬',
    title: 'Housing Discussions',
    content: 'Engage in thoughtful discussions on various housing topics.'
  },
  {
    logo: '🤝',
    title: 'Concert Series',
    content: 'Enjoy live performances from local bands and artists every weekend.'
  },

];
</script>

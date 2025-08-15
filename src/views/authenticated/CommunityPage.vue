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
        <h2 class="text-2xl font-bold mb-4">Explore Communities</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <!-- Community card template repeated for multiple communities -->
          <CommunityOutput
            v-for="(event, index) in events"
            :key="index"
            :event="event"
          />

        <!-- <div class="bg-white rounded-lg shadow p-5 flex flex-col">
            <div class="flex items-center space-x-3 mb-3">
              <span
                class="w-10 h-10 bg-green-100 text-green-600 rounded-full flex items-center justify-center font-semibold"
                >Bio</span
              >
              <div>
                <h3 class="font-semibold text-gray-800">Biology Club</h3>
                <p class="text-xs text-gray-500">850 members</p>
              </div>
            </div>
            <p class="text-sm text-gray-600 flex-1">
              Join us to explore the wonders of life science. From genetics to
              ecology, our members collaborate on research, share articles, and
              organize lab sessions.
            </p>
            <div class="mt-4 flex justify-between items-center">
              <a href="#" class="text-indigo-600 hover:underline text-sm"
                >View</a
              >
              <button
                class="bg-indigo-600 text-white px-3 py-1 rounded-md text-sm hover:bg-indigo-700"
              >
                Join
              </button>
            </div>
          </div> -->
          <!-- <div class="bg-white rounded-lg shadow p-5 flex flex-col">
            <div class="flex items-center space-x-3 mb-3">
              <span
                class="w-10 h-10 bg-pink-100 text-pink-600 rounded-full flex items-center justify-center font-semibold"
                >Art</span
              >
              <div>
                <h3 class="font-semibold text-gray-800">Arts Society</h3>
                <p class="text-xs text-gray-500">620 members</p>
              </div>
            </div>
            <p class="text-sm text-gray-600 flex-1">
              A haven for painters, sculptors, and creators of all kinds. Share
              your work, join art challenges, and organize exhibitions on
              campus.
            </p>
            <div class="mt-4 flex justify-between items-center">
              <a href="#" class="text-indigo-600 hover:underline text-sm"
                >View</a
              >
              <button
                class="bg-indigo-600 text-white px-3 py-1 rounded-md text-sm hover:bg-indigo-700"
              >
                Join
              </button>
            </div>
          </div>
          <div class="bg-white rounded-lg shadow p-5 flex flex-col">
            <div class="flex items-center space-x-3 mb-3">
              <span
                class="w-10 h-10 bg-yellow-100 text-yellow-600 rounded-full flex items-center justify-center font-semibold"
                >Math</span
              >
              <div>
                <h3 class="font-semibold text-gray-800">Mathematics Club</h3>
                <p class="text-xs text-gray-500">950 members</p>
              </div>
            </div>
            <p class="text-sm text-gray-600 flex-1">
              Delve into the world of numbers and theories. Participate in
              problem‑solving sessions, math competitions, and collaborative
              study groups.
            </p>
            <div class="mt-4 flex justify-between items-center">
              <a href="#" class="text-indigo-600 hover:underline text-sm"
                >View</a
              >
              <button
                class="bg-indigo-600 text-white px-3 py-1 rounded-md text-sm hover:bg-indigo-700"
              >
                Join
              </button>
            </div>
          </div>
          <div class="bg-white rounded-lg shadow p-5 flex flex-col">
            <div class="flex items-center space-x-3 mb-3">
              <span
                class="w-10 h-10 bg-blue-100 text-blue-600 rounded-full flex items-center justify-center font-semibold"
                >Eco</span
              >
              <div>
                <h3 class="font-semibold text-gray-800">Environmental Club</h3>
                <p class="text-xs text-gray-500">540 members</p>
              </div>
            </div>
            <p class="text-sm text-gray-600 flex-1">
              Passionate about sustainability and conservation? Join us to
              participate in cleanup drives, awareness campaigns, and green
              initiatives around campus.
            </p>
            <div class="mt-4 flex justify-between items-center">
              <a href="#" class="text-indigo-600 hover:underline text-sm"
                >View</a
              >
              <button
                class="bg-indigo-600 text-white px-3 py-1 rounded-md text-sm hover:bg-indigo-700"
              >
                Join
              </button>
            </div>
          </div>
          <div class="bg-white rounded-lg shadow p-5 flex flex-col">
            <div class="flex items-center space-x-3 mb-3">
              <span
                class="w-10 h-10 bg-purple-100 text-purple-600 rounded-full flex items-center justify-center font-semibold"
                >Lit</span
              >
              <div>
                <h3 class="font-semibold text-gray-800">Literature Circle</h3>
                <p class="text-xs text-gray-500">430 members</p>
              </div>
            </div>
            <p class="text-sm text-gray-600 flex-1">
              For lovers of books, poetry, and creative writing. Share
              recommendations, host readings, and collaborate on writing
              projects.
            </p>
            <div class="mt-4 flex justify-between items-center">
              <a href="#" class="text-indigo-600 hover:underline text-sm"
                >View</a
              >
              <button
                class="bg-indigo-600 text-white px-3 py-1 rounded-md text-sm hover:bg-indigo-700"
              >
                Join
              </button>
            </div>
          </div> -->
        </div>
        <!-- Create Community CTA -->
        <div class="mt-8 bg-white rounded-lg shadow p-6 text-center">
          <h2 class="text-lg font-semibold mb-2">
            Want to start your own community?
          </h2>
          <p class="text-sm text-gray-600 mb-4">
            If you can’t find what you’re looking for, create a new community
            for your interest or study group.
          </p>
          <button
            class="bg-green-500 text-white px-4 py-2 rounded-md hover:bg-green-600"
          >
            Create Community
          </button>
        </div>
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
    title: 'Study Group',
    content: 'Join us for weekly study sessions and collaborative learning.'
  },
  {
    logo: '💬',
    title: 'Discussion Club',
    content: 'Engage in thoughtful discussions on various topics.'
  },
  {
    logo: '🤝',
    title: 'Networking Event',
    content: 'Connect with professionals and expand your network.'
  },
  {
    logo: '🎨',
    title: 'Art Club',
    content: 'Explore your creativity and collaborate on art projects.'
  },
  {
    logo: '🎭',
    title: 'Drama Club',
    content: 'Join us for theatrical performances and drama workshops.'
  },
  {
    logo: '🎤',
    title: 'Music Club',
    content: 'Share your passion for music, collaborate on projects, and participate in jam sessions.'
  }
];
</script>

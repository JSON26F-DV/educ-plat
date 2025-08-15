<script setup>
  import PostLayout from '@/layouts/PostLayout.vue';
  const { event } = defineProps({
    event: {
      type: Array,
      required: true,
    },
  });
</script>

<template>
  <PostLayout class="w-auto">
    <div class="card-header flex items-center space-x-3 text-start">
      <span
        class="w-10 h-10 bg-indigo-100 text-indigo-600 rounded-full flex items-center justify-center font-semibold"
        > {{ event.logo }}</span
      >
      <div>
        <h6 class="font-semibold text-gray-800  ">
          {{ event.title }}
        </h6>
        <small class="text-xs text-gray-500">1.2K members</small>
      </div>
    </div>
    <div class="card-body">
            <p class="text-sm text-gray-600 flex-1">
              {{ event.content }}
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
      </PostLayout>
</template>



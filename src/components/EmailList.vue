<script>
export default {
  name: "EmailList",
  props: {
    emails: {
      type: Array,
      required: true,
    },
  },
};
</script>

<template>
  <div class="border border-gray-300 rounded-lg px-6 py-3">
    <div
      class="grid grid-cols-12 gap-4 border-b border-b-gray-300 px-6 py-2 mb-1 w-full"
      v-for="item in emails"
      :key="item?._id"
    >
      <div class="truncate col-span-12 sm:col-span-4 font-medium">
        {{ item?._source?.Subject }}
      </div>
      <div class="truncate col-span-12 sm:col-span-6">
        {{ item?._source?._body }}
      </div>
      <div class="col-span-12 sm:col-span-2 text-gray-400 text-right">
        {{ item?._source?.Date }}
      </div>
    </div>
    <div class="flex justify-center mt-6">
      <div class="flex space-x-2">
        <button
          class="bg-white hover:bg-gray-100 text-gray-500 font-semibold py-1 px-3 border border-gray-400 rounded shadow"
        >
          Previous
        </button>
        <button
          class="bg-white hover:bg-gray-100 text-gray-500 font-semibold py-1 px-3 border border-gray-400 rounded shadow"
        >
          Next
        </button>
      </div>
    </div>
  </div>
</template>

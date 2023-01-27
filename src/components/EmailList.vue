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
      class="border-b border-b-gray-300 px-6 py-2 mb-1 w-full flex justify-between"
      v-for="item in emails"
      :key="item.id"
    >
      <div>{{ item.first_name }}</div>
      <div>{{ item.email }}</div>
      <div class="text-gray-400 text-right">Fecha</div>
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

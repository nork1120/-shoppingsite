<template>
  <div class="btn-group" role="group" aria-label="First group">
    <button type="button" class="btn btn-outline-primary" :disabled="paa.has_pre == false"  @click="$emit('pag', paa.current_page-1)">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="16"
        height="16"
        fill="currentColor"
        class="bi bi-chevron-double-left"
        viewBox="0 0 16 16"
      >
        <path
          fill-rule="evenodd"
          d="M8.354 1.646a.5.5 0 0 1 0 .708L2.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0z"
        />
        <path
          fill-rule="evenodd"
          d="M12.354 1.646a.5.5 0 0 1 0 .708L6.707 8l5.647 5.646a.5.5 0 0 1-.708.708l-6-6a.5.5 0 0 1 0-.708l6-6a.5.5 0 0 1 .708 0z"
        />
      </svg>
    </button>
    <label
      :class="{ active: paa.current_page == e }"
      :for="e"
      class="btn btn-outline-primary"
      v-for="e in paa.total_pages"
      :key="e"
      >{{ e }}
      <input
        :id="e"
        type="radio"
        :disabled="page == e"
        v-model="page"
        :value="e"
        hidden
        @click="$emit('pag', e)"
    /></label>
    <button class="btn btn-outline-primary" :disabled="paa.has_next == false" @click="$emit('pag', paa.current_page+1)" >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="16"
        height="16"
        fill="currentColor"
        class="bi bi-chevron-double-right"
        viewBox="0 0 16 16"
      >
        <path
          fill-rule="evenodd"
          d="M3.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L9.293 8 3.646 2.354a.5.5 0 0 1 0-.708z"
        />
        <path
          fill-rule="evenodd"
          d="M7.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L13.293 8 7.646 2.354a.5.5 0 0 1 0-.708z"
        />
      </svg>
    </button>
  </div>
</template>


<script>
export default {
  data() {
    return {
      page: "1",
    };
  },
  props: ["paa"],
  methods: {},
};
</script>
<style lang="scss" scoped>


</style>
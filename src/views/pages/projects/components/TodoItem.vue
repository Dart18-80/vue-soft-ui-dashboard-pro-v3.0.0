<template>
  <li
    class="py-0 mb-3 border-0 list-group-item flex-column align-items-start ps-0"
  >
    <div class="checklist-item checklist-item-primary ps-2 ms-3">
      <div class="d-flex align-items-center">
        <soft-checkbox :id="checkboxId" :name="title" :checked="checked" />
        <h6 class="mb-0 text-sm text-dark font-weight-bold">{{ title }}</h6>
        <div class="dropdown float-lg-end ms-auto pe-4">
          <a
            :id="dropdownTableId"
            href="#"
            class="cursor-pointer"
            :class="{ show: showMenu }"
            data-bs-toggle="dropdown"
            aria-expanded="false"
            @click="showMenu = !showMenu"
          >
            <i class="fa fa-ellipsis-h text-secondary" aria-hidden="true"></i>
          </a>
          <ul
            class="px-2 py-3 dropdown-menu ms-sm-n4 ms-n5"
            :class="{ show: showMenu }"
            :aria-labelledby="dropdownTableId"
            style=""
          >
            <li v-for="({ label, route }, index) of action" :key="index">
              <a class="dropdown-item border-radius-md" :href="route">{{
                label
              }}</a>
            </li>
          </ul>
        </div>
      </div>
      <div class="mt-3 d-flex align-items-center ms-4 ps-1">
        <div>
          <p class="mb-0 text-xs text-secondary font-weight-bold">Date</p>
          <span class="text-xs font-weight-bolder">{{ date }}</span>
        </div>
        <div class="ms-auto">
          <p class="mb-0 text-xs text-secondary font-weight-bold">Project</p>
          <span class="text-xs font-weight-bolder">{{ projectId }}</span>
        </div>
        <div class="mx-auto">
          <p class="mb-0 text-xs text-secondary font-weight-bold">Company</p>
          <span class="text-xs font-weight-bolder">{{ company }}</span>
        </div>
      </div>
    </div>
    <hr class="mt-4 mb-0 horizontal dark" />
  </li>
</template>

<script>
import SoftCheckbox from "@/components/SoftCheckbox.vue";

export default {
  name: "TodoItem",
  components: {
    SoftCheckbox,
  },
  props: {
    title: {
      type: String,
      default: "",
    },
    checkboxId: {
      type: String,
      default: "",
    },
    dropdownTableId: {
      type: String,
      default: "",
    },
    date: {
      type: String,
      default: "",
    },
    projectId: {
      type: String,
      default: "",
    },
    company: {
      type: String,
      default: "",
    },
    checked: {
      type: Boolean,
      default: false,
    },
    action: {
      type: Array,
      default: () => [],
      label: String,
      route: String,
    },
  },
  data() {
    return {
      showMenu: false,
    };
  },
};
</script>

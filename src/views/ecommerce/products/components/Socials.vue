<template>
  <div
    class="p-3 bg-white card multisteps-form__panel border-radius-xl"
    data-animation="FadeIn"
  >
    <h5 class="font-weight-bolder">Socials</h5>
    <div class="multisteps-form__content">
      <div class="mt-3 row">
        <div class="col-12">
          <label>Shoppify Handle</label>
          <soft-input
            class="multisteps-form__input"
            type="text"
            placeholder="@soft"
          />
        </div>
        <div class="mt-3 col-12">
          <label>Facebook Account</label>
          <soft-input
            class="multisteps-form__input"
            type="text"
            placeholder="https://..."
          />
        </div>
        <div class="mt-3 col-12">
          <label>Instagram Account</label>
          <soft-input
            class="multisteps-form__input"
            type="text"
            placeholder="https://..."
          />
        </div>
      </div>
      <div class="row">
        <div class="mt-4 button-row d-flex col-12">
          <soft-button
            color="secondary"
            variant="gradient"
            class="mb-0 js-btn-prev"
            title="Prev"
            @click="this.$parent.prevStep"
            >Prev</soft-button
          >
          <soft-button
            type="button"
            color="dark"
            variant="gradient"
            class="mb-0 ms-auto js-btn-next"
            title="Next"
            @click="this.$parent.nextStep"
            >Next</soft-button
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SoftInput from "@/components/SoftInput.vue";
import SoftButton from "@/components/SoftButton.vue";

export default {
  name: "Socials",
  components: {
    SoftInput,
    SoftButton,
  },
};
</script>

<template>
  <div class="ingredients__sauce">
    <p>Основной соус:</p>

    <label
      v-for="sauce in sauces"
      :key="sauce.id"
      class="radio ingredients__input"
    >
      <RadioButton
        name="sauce"
        :params="sauce"
        :checked="order.sauce === sauce.id"
        @updateOrder="$emit('updateOrder', $event)"
      />
      <span>
        {{ sauce.name }}
      </span>
    </label>
  </div>
</template>

<script>
import RadioButton from "@/common/components/RadioButton";

export default {
  name: "BuilderSauceSelector",
  props: {
    sauces: {
      type: Array,
      default: () => [],
    },
    order: {
      type: Object,
      required: true,
    },
  },
  components: { RadioButton },
};
</script>

<template>
  <div class="accordion-item" :class="{ active: isOpen }">
    <div class="accordion-item__body">
      <h3 class="accordion-item__body--title" @click="toggle">
        {{ item.title }}
      </h3>
      <p class="accordion-item__body--description" v-if="isOpen">
        {{ item.body }}
      </p>
    </div>
    <div class="accordion-item__icon">
      <svg
        width="10"
        height="7"
        @click="toggle"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M1 .799l4 4 4-4"
          stroke="#F47B56"
          stroke-width="2"
          fill="none"
          fill-rule="evenodd"
        />
      </svg>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AccordionItem',

  props: ['item', 'isOpen'],

  data() {
    return {};
  },

  methods: {
    toggle() {
      this.$emit('toggled', this.$vnode.key);
    }
  }
};
</script>

<style lang="css" scoped>
.accordion-item {
  display: flex;
  justify-content: space-between;
  padding: 1rem 0;
  border-bottom: 1px solid hsl(240, 5%, 91%);
}

.accordion-item__icon {
  padding: 0 1rem;
}

.accordion-item__icon > svg {
  cursor: pointer;
  transition: transform 0.3s ease-in-out;
}

.accordion-item__body--title {
  color: hsl(237, 12%, 33%);
  font-weight: 400;
  cursor: pointer;
}

.accordion-item__body--description {
  color: hsl(240, 6%, 50%);
  font-weight: 400;
  line-height: 1.2rem;
  padding-top: 1rem;
}

/* Accordion Active Style */

.accordion-item.active .accordion-item__body--title {
  font-weight: 700;
}

.accordion-item.active .accordion-item__icon > svg {
  transform: rotate(180deg);
}
</style>

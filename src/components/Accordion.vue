<template>
  <div class="accordion">
    <accordion-item
      v-for="(item, index) in items"
      :item="item"
      :is-open="selctedAccordionIndex == index"
      @toggled="onToggle"
      :key="index"
    />
  </div>
</template>

<script>
import AccordionItem from './AccordionItem.vue';

export default {
  name: 'Accordion',

  props: ['items'],

  components: {
    AccordionItem
  },

  data() {
    return {
      selctedAccordionIndex: null
    };
  },

  methods: {
    onToggle(index) {
      if (this.selctedAccordionIndex == index) {
        return (this.selctedAccordionIndex = null);
      }

      this.selctedAccordionIndex = index;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>

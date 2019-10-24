<template>
    <dl class="accordion box" role="presentation">
        <accordion-item 
            v-for="response in mediaResponses"
            :multiple="multiple"
            :response="response"
            :groupId="groupId"
            :key="response.id"
        ></accordion-item>
    </dl>
</template>

<script>
import AccordionItem from './AccordionItem.vue';
export default {
    name: 'Accordion',
    components: {
        AccordionItem
    },
    props: {
        mediaResponses: {
            type: Array,
            required: true
        },
        multiple: {
            type: Boolean,
            default: false
        }
    },
    data() {
        return {
            groupId: null
        }
    },
    mounted() {
        this.groupId = this.$el.id
    }
}
</script>
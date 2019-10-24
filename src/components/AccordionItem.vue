<template>
    <div :id="groupId + '-' + response.id" :class="['accordion-item', { 'is-active': response.active }, { 'draft': response.draft }]">

        <dt class="accordion-item-title">
            <button @click="toggle" class="accordion-item-trigger">
                <div>
                    <!-- NB: RETHINK THE DATE. 25 - 4 MAY DOESN'T WORK -->
                    <time>{{ response.time }}</time>
                    <h4 class="accordion-item-title-text">{{ response.title }}
                        <template v-if="response.draft">
                            <span class="badge badge-secondary">Draft</span>
                        </template>
                        <template v-else-if="response.new">
                            <span class="badge badge-primary">New</span>
                        </template>
                        <template v-else></template>
                    </h4>
                </div>
                <span class="accordion-item-trigger-icon"></span>
            </button>
        </dt>
        <transition name="accordion-item" @enter="startTransistion" @after-enter="endTransition" @before-leave="startTransistion" @after-leave="endTransition">
            <dd v-if="response.active" class="accordion-item-details">
                <div class="accordion-item-details-inner">
                    <div class="embed-container">
                        <iframe :src="response.videoSrc" frameborder="0" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>
                    </div>

                    <h3 class="section-heading">Agency's notes</h3>
                    <p>{{ response.notes }}</p>
                    <h3 class="section-heading">Attachments</h3>

                    <ul class="media-response-attachments">
                        <!-- <template v-for="response in mediaResponses">
                            <li v-for="attachment in response.attachments" :key="attachment.id">

                                <figure class="img-wrapper">
                                    <img class="upload-img" :src="attachment.thumbnail_url"/>
                                </figure>
                                <figcaption>{{ attachment.title }}</figcaption>
                                <span>{{ attachment.size }}</span>

                            </li>
                        </template> -->
                    </ul>
                </div>
            </dd>
        </transition>
    </div>
</template>

<script>
    export default {
        name: 'AccordionItem',
        props: [
            'response',
            'multiple',
            'groupId'
        ],
        methods: {
            toggle(event) {
                if (this.multiple) this.response.active = !this.response.active
                else {
                    this.$parent.$children.forEach((response, index) => {
                        if (response.$el.id === event.currentTarget.parentElement.parentElement.id) response.response.active = !response.response.active
                        else response.response.active = false
                    })
                }
            },
            startTransistion(el) {
                el.style.height = el.scrollHeight + 'px'
            },
            endTransition(el) {
                el.style.height = ''
            }
        },
    }
</script>

<style lang="scss" scoped>
    .badge {
        margin-left: 0.25rem;
    }
    // time {
    //     @include section-heading();
    // }

    .embed-container {
        position: relative;
        padding-bottom: 56.25%;
        height: 0;
        overflow: hidden;
        max-width: 100%;
        margin-bottom: 1rem;
        iframe, object, embed {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
    }
</style>

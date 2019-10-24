<template>
    <aside class="media-responses">
        <accordion id="accordion-example-1" :mediaResponses="mediaResponses"></accordion>
        <!-- <div v-for="response in mediaResponses" key="response.id">
            <h2>{{ response.title }}</h2>
        </div> -->
    </aside>
</template>

<script>
import Accordion from './Accordion';
export default {
    name: 'MediaResponses',
    components:{
        Accordion
    },
    data () {
        return {
            mediaResponses: [
                {
                    id: 0,
                    active: false,
                    draft: '',
                    title: '',
                    time: '',
                    notes: '',
                    videoSrc: '',
                    attachments: [
                        {
                            title: '',
                            size: '',
                            thumbnail_url: ''
                        },
                        {
                            title: '',
                            size: '',
                            thumbnail_url: ''
                        }
                    ]
                },
                {
                    id: 1,
                    active: false,
                    new: false,
                    draft: true,
                    title: 'Crushing spirits',
                    time: '4-30 May 2018',
                    notes: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
                    videoSrc: 'https://player.vimeo.com/video/289251280',
                    attachments: [
                        {
                            title: 'attachment1.pdf',
                            size: '122kb',
                            thumbnail_url: ''
                        },
                        {
                            title: 'attachment1.pdf',
                            size: '122kb',
                            thumbnail_url: ''
                        }
                    ]
                },
                {
                    id: 2,
                    active: false,
                    new: true,
                    draft: false,
                    title: 'Soundtracks',
                    time: '8-9 July 2019',
                    notes: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
                    videoSrc: 'https://player.vimeo.com/video/303045251',
                    attachments: [
                        {
                            title: 'attachment1.pdf',
                            size: '122kb',
                            thumbnail_url: ''
                        },
                        {
                            title: 'attachment1.pdf',
                            size: '122kb',
                            thumbnail_url: ''
                        }
                    ]
                },
                {
                    id: 3,
                    active: false,
                    new: false,
                    draft: false,
                    title: 'The Man who sold everything',
                    time: '2-9 June 2019',
                    notes: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
                    videoSrc: 'https://player.vimeo.com/video/66140585',
                    attachments: [
                        {
                            title: 'attachment1.pdf',
                            size: '122kb',
                            thumbnail_url: ''
                        },
                        {
                            title: 'attachment1.pdf',
                            size: '122kb',
                            thumbnail_url: ''
                        }
                    ]
                }
            ],
        }
    },
}
</script>
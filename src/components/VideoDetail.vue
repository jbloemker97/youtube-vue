<template>
    <div v-if="video" class="col-md-8">
        <div class="embed-responsive embed-responsive-16by9">
            <iframe class="embed-responsive-item" :src="videoUrl" />
        </div>
        <div class="details">
            <h4>{{ video.snippet.title }}</h4>
            <p>{{ video.snippet.description }}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'videoDetail',
        props: ['video'],
        computed: {
            videoUrl () {
                const { videoId } = this.video.id;

                return `https://youtube.com/embed/${videoId}`;
            }
        }
    }
</script>

<style>
    .details {
        border: 1px solid #ddd;
        border-radius: 4px;
        margin-top: 10px;
        padding: 10px;
    }
</style>
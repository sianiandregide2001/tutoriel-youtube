<template>
    <RouterLink :to="`video/${videoInfo.video.videoId}`">
        <div class="w-40 h-44 m-2 P-2 rounded-xl bg-white shadow-ld"
        @mouseover="isHovering = true"
        @mouseleave="isHovering = false">
            <img  :src="
            isHovering && videoInfo.video.movingThumbnails &&
            videoInfo.video.movingThumbnails.length > 0
            ?videoInfo.video.movingThumbnails[0].url
            :videoInfo.video.thumbnails[0].url" alt="Thumbnails" class="rounded-xl">

            <h3 class="title my-2 text-xxs">  {{videoInfo.video.title }} </h3>
            <h4 class="text-xxs">SIANI DEV</h4>
            <p class="text-xs">
                 {{videoInfo.video.stats.views}} views -
                 {{videoInfo.video.publishedTimeText }}
                </p> 
        </div>
    </RouterLink>
   

</template>

<script>
export default {
    name: "VideoCard",
    props: {
        videoInfo: Object,
    },
    data() {
         return{
            isHovering: false
         }
    }
}
</script>
<style>
.title {
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
    overflow: hidden;
    text-overflow: ellipsis;
    line-height: 1.5em;
    font-weight: bolder;


}
</style>
<template>
    
    <div class="sm:px-32 flex flex-wrap justify-center">
        <VideoCard v-for="video in videos" :key="video.id" :videoInfo="video"/>
    </div>
</template>

<script>
import VideoCard from "../components/VideoCard.vue";
export default{
    name: "HomeFeed",
    components: {
        VideoCard,
    },
    data() {
        return{
            videos:[],
        };
    },
    mounted() {
        const url = 'https://youtube138.p.rapidapi.com/channel/videos/?id=UCoCqCzNVK5KVBV0Kw94mqYw&filter=videos_latest';
const options = {
	method: 'GET',
	headers: {
		'X-RapidAPI-Key': '4500d4d8b1msh4997c0cefe9d848p141c8cjsna1421b4ee289',
		'X-RapidAPI-Host': 'youtube138.p.rapidapi.com'
	}
};
fetch(url, options).then(response => response.json()).then(data => this.videos = data.contents)
.catch(error => console.error("problem fetching the videos", error));

    },
};
</script>

<template>
    <div class="px-8 flex flex-col items-center">
        <div class="video-container sm:w-2/3 w-4/5">
            <iframe :src="`https://youtube.com/embed/${$route.params.id}`" class="video rounded-xl shadow-lg"> </iframe>
        </div>
    </div>
    <h3 class="mt-4 text-center text-lg">  {{ videoInfo.title }}  </h3>
</template>

<script>
export default{
    name: "VideoDetails",
    data(){
        return{
            videoInfo:[]
        };
    },
    mounted() {
        const url = 'https://youtube138.p.rapidapi.com/video/details/?id= '+this.$route.params.id;
const options = {
	method: 'GET',
	headers: {
		'x-rapidapi-key': '4500d4d8b1msh4997c0cefe9d848p141c8cjsna1421b4ee289',
		'x-rapidapi-host': 'youtube138.p.rapidapi.com'
	}
};
fetch(url, options)
.then(response => response.json())
.then(data => this.videoInfo = data)
.catch (error => console.error("Error fetching video :", error));
    },
};
</script>
<style>
.video-container {
    padding-top: 40%;
    position: relative;
    margin: 0 auto 10px auto;
}
.video{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
</style>
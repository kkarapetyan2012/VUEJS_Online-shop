<template>
    <div class="container">
        <div class="row">
            <div class="col-md-12">
                <div class="video-list">
                    <div class="video-container">
                        <iframe width="100%" height="600px" :src="this.activeVideo.youtubeURL" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
                    </div>
                    <h3>{{this.activeVideo.title}}</h3>
                    <div  @click="chooseVideo(video)" :key="video.id" v-for="video in videos" class="thumbnail">
                        <!-- <div class="thumbnail-img">
                            <img :src="video.thumbnail" />
                        </div> -->
                        <div class="thumbnail-info">
                            <!-- <h3>{{video.title}}</h3>
                            <p>{{video.creator}}</p> -->
                            <p class="thumbnail-views">{{video.views}} Views</p>
                        </div>
                        <button @click="addLike">Like</button>
                    </div>
                    
                </div>
            </div>
        </div>
        
    </div>
</template>

<script>
let videos = [
  {
    id: 1,
    title: "iPhone X Camera Test!",
    thumbnail:
      "https://i.ytimg.com/vi/jn9mHzXJIV0/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLAvJvk4k_UNB9nst4pFP-txM1TLZA",
    youtubeURL: "https://www.youtube.com/embed/YQ1uSKPrcy8",
    creator: "Marques Brownlee",
    likes: 0,
    views: 0
  },
//   {
//     id: 2,
//     title: "Dope Tech: Camera Robots!",
//     thumbnail:
//       "https://i.ytimg.com/vi/UIwdCN4dV6w/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLDhlan32jHSvicGZezDFPjAOdXGUA",
//     youtubeURL: "https://www.youtube.com/embed/UIwdCN4dV6w",
//     creator: "Marques Brownlee",
//     likes: 0,
//     views: 0
//   },
//   {
//     id: 3,
//     title: "Let's Talk About Tesla Roadster 2020!",
//     thumbnail:
//       "https://i.ytimg.com/vi/ctx4YBEdOxo/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLBDnlrC2rVwXamNkicEEbc3Mf4T0w",
//     youtubeURL: "https://www.youtube.com/embed/ctx4YBEdOxo",
//     creator: "Marques Brownlee",
//     likes: 0,
//     views: 0
//   },
//   {
//     id: 4,
//     title: "Talking Tech with Neil deGrasse Tyson!",
//     thumbnail:
//       "https://i.ytimg.com/vi/pqQrL1K0Z5g/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLA5hTiwkz4Tr1w1hSMhPlwtmQeyYw",
//     youtubeURL: "https://www.youtube.com/embed/pqQrL1K0Z5g",
//     creator: "Marques Brownlee",
//     likes: 0,
//     views: 0
//   },
//   {
//     id: 5,
//     title: "The Apple Ecosystem: Explained!",
//     thumbnail:
//       "https://i.ytimg.com/vi/KB4_WIPE7vo/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLCCxXm7aoPShOwON74nhMlGYMUkHw",
//     youtubeURL: "https://www.youtube.com/embed/KB4_WIPE7vo",
//     creator: "Marques Brownlee",
//     likes: 0,
//     views: 0
//   }
];

export default {
  data () {
    return {
      videos,
      activeVideo: videos[0]
    }
  },
  methods:{
    chooseVideo(video){
        //SET VIDEO AS ACTIVE VIDEO
        this.activeVideo = video;
        //INCREASE THE VIDEOS VIEWS BY 1
        video.views += 1;
    },
    addLike(){
        this.activeVideo.likes += 1;
    }
  }
}

</script>

<style>
.video-list {
    padding: 15px 0;
}

.thumbnail{
    display:flex;
    justify-content: space-between
  }

.thumbnail img{
    width:168px;
}

.thumbnail-info{
    margin-left:20px;
}

.thumbnail h3{
    font-size:16px;
}

h3,
p{
    margin:0;
    padding:0;
}

.thumbnail-views{
    font-size:14px;
}

.video-player{
    display:flex;
    width:1200px;
    margin:auto;
}

.row{
    display:flex;
}

button{
    background:#D0021B;
    color:white;
    border:none;
    outline:none;
    padding:10px 20px;
}


</style>

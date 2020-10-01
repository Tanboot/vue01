<template>
<div>
    <img src="https://media.discordapp.net/attachments/402366472665432064/761105433754599434/pngwing.com.png?width=396&height=396" alt="" height="150px" width="150px" class="img-fluid mx-auto" />
    <br />
    <br />
    <div class="row">
        <div class="col">
        </div>
        <div class="col">
            <input class="form-control ds-input " type=" text" v-model="keyword" placeholder="กรุณากรอกชื่อเพลง" />
            <br />
            <button @click="searchData" class="btn btn-warning">Search Music</button>
            <!--{{resultData}} -->
        </div>
        <div class="col">
        </div>
    </div>
    <br />
    <br />
    <div class="row">
        <div class="col-sm"></div>
        <div class="col-sm">
            <b-card-group columns>
                <div v-for="data in resultData" :key="data.trackId">
                    <b-card :title="data.title" :img-src="data.artworkUrl100" img-alt="Image" img-top tag="article" style="max-width: 25rem;" class="mb-2">
                        <b-card-text>{{ data.trackName }}</b-card-text>
                        <b-card-text>{{ data.artistName }}</b-card-text>
                        <audio controls >
                            <source :src="data.previewUrl" type="audio/mpeg" />
                        </audio>
                        <b-button :href="data.trackViewUrl" variant="secondary">Play</b-button>
                    </b-card>
                </div>
            </b-card-group>
        </div>
        <div class="col-sm"></div>
    </div>
</div>
</template>

<script>
import axios from "axios";
export default {
    data() {
        return {
            resultData: null,
            keyword: "",
        };
    },
    methods: {
        searchData() {
            axios
                .get(
                    "https://itunes.apple.com/search?term=" + this.keyword + "&limit=15"
                )
                .then((response) => {
                    this.resultData = response.data.results;
                })
                .catch((err) => {
                    console.log(err);
                });
        },
    },
};
</script>

<style>
.card {
    background-image: url('https://media.discordapp.net/attachments/402366472665432064/761102799060336640/Dt-EDLmU8AIm-u0.jpg?width=240&height=427');
}
</style>
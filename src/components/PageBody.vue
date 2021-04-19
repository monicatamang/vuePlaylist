<template>
    <section>
        <article>
            <h1>Song List</h1>
            <song-list @songCardClicked="moveSongCard" v-for="song in songList" :key="song.id" :songObject="song"></song-list>
        </article>
        <article>
            <h1>Playlist</h1>
            <play-list v-for="selectedSong in playListSongs" :key="selectedSong.id" :playListSong="selectedSong"></play-list>
        </article>
    </section>
</template>

<script>
    import SongList from "./SongList.vue";
    import PlayList from "./PlayList.vue";

    export default {
        name: "page-body",
        components: {
            SongList,
            PlayList,
        },
        methods: {
            moveSongCard: function(data) {
                document.getElementById(`song${data.id}`).remove();
                console.log(data.id);

                if(data.id === 1) {
                    this.selectedSong1.title = data.title;
                    this.selectedSong1.artist = data.artist;
                    this.playListSongs.push(this.selectedSong1);
                } if(data.id === 2) {
                    this.selectedSong2.title = data.title;
                    this.selectedSong2.artist = data.artist;
                    this.playListSongs.push(this.selectedSong2);
                } if(data.id === 3) {
                    this.selectedSong3.title = data.title;
                    this.selectedSong3.artist = data.artist;
                    this.playListSongs.push(this.selectedSong3);
                } if(data.id === 4) {
                    this.selectedSong4.title = data.title;
                    this.selectedSong4.artist = data.artist;
                    this.playListSongs.push(this.selectedSong4);
                } if(data.id === 5) {
                    this.selectedSong5.title = data.title;
                    this.selectedSong5.artist = data.artist;
                    this.playListSongs.push(this.selectedSong5);
                } if(data.id === 6) {
                    this.selectedSong6.title = data.title;
                    this.selectedSong6.artist = data.artist;
                    this.playListSongs.push(this.selectedSong6);
                } if(data.id === 7) {
                    this.selectedSong7.title = data.title;
                    this.selectedSong7.artist = data.artist;
                    this.playListSongs.push(this.selectedSong7);
                } if(data.id === 8) {
                    this.selectedSong8.title = data.title;
                    this.selectedSong8.artist = data.artist;
                    this.playListSongs.push(this.selectedSong8);
                } if(data.id === 9) {
                    this.selectedSong9.title = data.title;
                    this.selectedSong9.artist = data.artist;
                    this.playListSongs.push(this.selectedSong9);
                } if(data.id === 10) {
                    this.selectedSong10.title = data.title;
                    this.selectedSong10.artist = data.artist;
                    this.playListSongs.push(this.selectedSong10);
                }
            },
        },
        data: function() {
            return {
                playListSongs: [],
                selectedSong1: {
                    id: 11,
                    title: "",
                    artist: ""
                },
                selectedSong2: {
                    id: 12,
                    title: "",
                    artist: ""
                },
                selectedSong3: {
                    id: 13,
                    title: "",
                    artist: ""
                },
                selectedSong4: {
                    id: 14,
                    title: "",
                    artist: ""
                },
                selectedSong5: {
                    id: 15,
                    title: "",
                    artist: ""
                },
                selectedSong6: {
                    id: 16,
                    title: "",
                    artist: ""
                },
                selectedSong7: {
                    id: 17,
                    title: "",
                    artist: ""
                },
                selectedSong8: {
                    id: 18,
                    title: "",
                    artist: ""
                },
                selectedSong9: {
                    id: 19,
                    title: "",
                    artist: ""
                },
                selectedSong10: {
                    id: 20,
                    title: "",
                    artist: ""
                },
                songList: [
                    {
                        id: 1,
                        title: `One Dance`,
                        artist: `Drake`
                    },
                    {
                        id: 2,
                        title: `Cheap Thrills`,
                        artist: `Sia`
                    },
                    {
                        id: 3,
                        title: `Bad Ones`,
                        artist: `Tate McRae`
                    },
                    {
                        id: 4,
                        title: `Never Forget You`,
                        artist: `Zara Larsson`
                    },
                    {
                        id: 5,
                        title: `Youth (feat. Khalid)`,
                        artist: `Shawn Mendes`
                    },
                    {
                        id: 6,
                        title: `Better Now`,
                        artist: `Post Malone`
                    },
                    {
                        id: 7,
                        title: `Same Squad`,
                        artist: `P-Lo`
                    },
                    {
                        id: 8,
                        title: `Memories`,
                        artist: `Maroon 5`
                    },
                    {
                        id: 9,
                        title: `Teenage Dream`,
                        artist: `Katy Perry`
                    },
                    {
                        id: 10,
                        title: `One Call Away`,
                        artist: `Charlie Puth`
                    },
                ],
            }
        },
    }
</script>

<style scoped>
    section {
        display: grid;
        place-items: center;
        grid-template-columns: 1fr 1fr;
    }

    article {
        display: grid;
        place-items: center;
        row-gap: 20px;
        width: 30vw;
    }
</style>
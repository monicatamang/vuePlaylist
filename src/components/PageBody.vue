<template>
    <section>
        <article>
            <h1>Song List</h1>
            <song-list @songCardClicked="moveSongCard" v-for="song in songList" :key="song.id" :songObject="song"></song-list>
        </article>
        <article>
            <h1>Playlist</h1>
            <play-list v-for="selectedSong in playListSongs" :key="selectedSong.id" :playListSong="selectedSong"></play-list>
            <play-list></play-list>
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
                
                this.playListSongs.push(this.selectedSong);
                this.songTitle = data.title;
                this.songArtist = data.artist;
                this.selectedSong.id = data.id;
            },
        },
        data: function() {
            return {
                playListSongs: [],
                selectedSong: {
                    id: undefined,
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
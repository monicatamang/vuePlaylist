<template>
    <section>
        <article>
            <h1>Song List</h1>
            <song-list @songCardClicked="moveSongCard" v-for="song in songList" :key="song.id" :songObject="song"></song-list>
        </article>
        <article>
            <h1>Playlist</h1>
            <play-list :title="selectedSongTitle" :artist="selectedSongArtist"></play-list>
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
                console.log(data.title);
                console.log(data.artist);
                document.getElementById(`song${data.id}`).remove();
                this.selectedSongTitle = data.title;
                this.selectedSongArtist = data.artist;
                console.log(this.songSelection);
            }
        },
        data() {
            return {
                selectedSongTitle: undefined,
                selectedSongArtist: undefined,
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
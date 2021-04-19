<template>
    <section>
        <article>

            <h1>Song List</h1>

            <!-- Creating a for-loop that will render each div tag with the title and artist of the song inside it -->
            <!-- Passing the props as an attribute so it can be used in the song list component as variables -->
            <!-- Adding the songCardClicked event as an attribute which calls the moveSongCard function when a song card is clicked -->
            <song-list @songCardClicked="addToPlayList" v-for="song in userSongList" :key="song.id" :songObject="song"></song-list>

        </article>

        <article>

            <h1>Playlist</h1>

            <!-- Passing the props as an attribute so it can be used as variables in the song list component -->
            <!-- Creating a for-loop that will render each div tag with the title and artist of the selected song inside it -->
            <play-list @playListSongClicked="addToSongList" v-for="selectedSong in userPlayList" :key="selectedSong.id" :playListObject="selectedSong"></play-list>

        </article>
    </section>
</template>

<script>

    // Importing the song list and playlist components into the body component
    import SongList from "./SongList.vue";
    import PlayList from "./PlayList.vue";

    // Registering the song list and playlist components
    export default {
        name: "page-body",
        components: {
            SongList,
            PlayList,
        },

        methods: {

            // When a song card is clicked from the playlist, the addSongCard function is called and receives the object that was passed from the playlist component
            addToSongList: function(data) {

                // Removing the selected song card from the playlist
                document.getElementById(`playListSong${data.id}`).remove();

                // Creating an object with the title and artist of the song that was removed from the playlist and adding it to the song list array
                // Modified the id each time the user clicks on the song card from the playlist to avoid having duplicate keys
                this.userSongList.push(
                    {
                        id: `${data.id}.1`,
                        title: `${data.title}`,
                        artist: `${data.artist}`
                    }
                )
            },

            // When a song card is clicked from the song list, the moveSongCard function is called and receives the object that was passed from the song list component
            addToPlayList: function(data) {

                // Removing the selected song card from the song list
                document.getElementById(`song${data.id}`).remove();

                // Creating an object with the title and artist of the song that was removed from the song list and adding it to the playList array
                this.userPlayList.push(
                    {
                        id: `${data.id}`,
                        title: `${data.title}`,
                        artist: `${data.artist}`
                    }
                )
            },
        },

        data: function() {
            return {

                // Creating an empty array so that it can be added with songs when the user clicks on a song card
                userPlayList: [],

                // Creating an array of 10 songs as objects
                userSongList: [
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
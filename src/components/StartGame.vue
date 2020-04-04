<template>
    <div class="container">
        <div class="row py-3 border">
            <div class="col">
                <button class = "btn btn-primary btn-xl"
                @click="startgame"
                >
                    Start New Game
                </button>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    props : [
        'startgame',
    ],
    methods: {
    }
}
</script>

<style>
.boder{
    border: 2px solid black;
}
</style>
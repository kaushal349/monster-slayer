<template>
    <div class="container py-5">
        <div class="row">
            <div class="col border">
                <div class="list-group list-group-flush text-center"
                v-for="(log,idx) in logs"
                :key ="idx"
                >
                    <li class="list-group-item"
                    :class="{'playerattackclass': log.isplayer, 'monsterattackclass': !log.isplayer}"
                    >
                    {{log.text}}
                    </li>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    props : [
        'logs'
    ]
}
</script>

<style>
/* .boder{
    border: 2px solid black;
} */
.playerattackclass{
    background: lightblue !important;
}
.monsterattackclass{
    background: lightcoral !important;
}
</style>
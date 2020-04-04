<template>
    <div class="container">
        <div class="row py-3 border">
            <div class="col">
                <button class = "btn btn-success btn-block"
                @click="attack"
                >
                    Attack
                </button>
            </div>
            <div class="col">
                <button class = "btn btn-danger btn-block"
                @click="specialattack"
                >
                    Special Attack
                </button>
            </div>
            <div class="col">
                <button class = "btn btn-info btn-block"
                @click="heal"
                >
                    Heal
                </button>
            </div>
            <div class="col">
                <button class = "btn btn-warning btn-block"
                @click="giveup"
                >
                    Giveup
                </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: [
        'attack',
        'specialattack',
        'heal',
        'giveup',
    ]
}
</script>

<style>
.boder{
    border: 2px solid black;
}
</style>
<template>
    <div class="container py-5">
    <div class="row">
      <div class="col">
        <h3 class = "py-3"><strong>Player</strong></h3>
        <div class="progress bg-secondary" style="height:20px">
          <div class="progress-bar bg-success" 
          :style="{width: playerhealth + '%'}" >
          <strong>{{ playerhealth }}</strong>
          </div>
        </div>
      </div>
      <div class="col">
        <h3 class = "py-3"><strong>Monster</strong></h3>
        <div class="progress bg-secondary" style="height:20px">
          <div class="progress-bar bg-success"
          :style="{width: monsterhealth + '%'}"
          >
          <strong>{{ monsterhealth }}</strong>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    props: [
        'playerhealth',
        'monsterhealth',
    ]
}
</script>
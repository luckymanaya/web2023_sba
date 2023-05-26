<script>
  export let locationData;
  export let img;
</script>

<div class="card">
  <div class="image" style="background-image: url({img});" />
  <div class="info">
    <h1 class="text name">Evil Rick</h1>
    <h3 class="text status">
      <div class="dead" />
      Dead - Humanoid
    </h3>

    <h3 class="text locationLabel">First seen in:</h3>
    <h3 class="text location"><a href="/location">{locationData}</a></h3>
  </div>
</div>

<style>
  .text {
    font-family: sans-serif;
    color: white;
  }
  .card {
    background: #333;
    overflow: hidden;
    height: 240px;
    display: flex;
    border-radius: 20px;
  }

  .image {
    width: 30%;
    background-size: cover;
    background-position: center;
  }

  .info {
    padding: 0.8rem;
  }

  .dead {
    background: firebrick;
    width: 10px;
    height: 10px;
    border-radius: 100%;
    margin-right: 10px;
  }
  .status {
    display: flex;
    align-items: center;
  }

  .locationLabel {
    color: #777;
    font-size: 16px;
    margin: 0 0 5px;
  }

  .location {
    font-size: 16px;
    margin-bottom: 20px;
    margin-inline: 0;
    margin-top: 0;
  }
  .location a {
    color: white;
  }
</style>

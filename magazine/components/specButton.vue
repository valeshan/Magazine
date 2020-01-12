<template>
  <div class="button-container">
  <p>BUTTON</p>
    <div class="location-button">
      <h1>+</h1>
    </div>
  </div>
</template>

<script>

export default {
  
}
</script>

<style lang="scss">


.button-container{
  font-family: 'Muli';
  border: 1px solid #FE7010;
  width: 11em;
  height: 40px;
  margin-top: 2em;
  margin-bottom: 2em;
  display: flex;
  position: relative;
  align-items: center;
  justify-content: space-between;
  p{
    color: #27198C;
    margin: 0 auto;
    font-size: 11px;
    font-weight: 900;
    letter-spacing: 0.5px;
    margin-left: 2em;
  }
}

.location-button{
  background-color: #FE7010;
  padding: 0 8px;
  height: 100%;
  display: flex;
  align-items: center;
  h1{
    opacity: 0.4;
    line-height: 1;
    color: white;
  }
}
</style>
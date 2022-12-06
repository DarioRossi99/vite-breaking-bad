<script>

export default{

};
</script>

<template>
  <section>
      <div class="logo-container d-flex">
        <img src="../assets/img/logo-png-popsocket-rick-and.png" class="logo" alt="">
        <h1>Rick and Morty</h1>
      </div>
  
    <div class="container">
      <div class="dropdown">
        <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenu2" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Select Category
        </button>
        <div class="dropdown-menu" aria-labelledby="dropdownMenu2">
          <button class="dropdown-item" type="button">Action</button>
          <button class="dropdown-item" type="button">Another action</button>
          <button class="dropdown-item" type="button">Something else here</button>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
@use "../styles/general.scss" as * ;

section{
  background-color: rgb(46, 58, 70);
  padding: 3rem;
}
.logo-container{
  align-items: center;
  color: white;
  margin-bottom: 2rem;
}
.logo{
  width: 100PX;
  border-radius: 50%;
  margin-right: 2rem;
}

.container{
  background-color: rgb(46, 58, 70);
}

.btn{
  background-color: white;
  color: black;
}
</style>

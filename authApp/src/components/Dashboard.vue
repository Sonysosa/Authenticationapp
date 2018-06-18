<template>
 <div class="row">
  <div class="col-xs-4 col-sm-4 col-md-4 col-lg-4">
    <div class="side-nav">
      <ul>
        <li>Dashboard</li>
        <li>Home</li>
        <li>Post</li>
        <li>Comments</li>
        <li>Users</li>
        <li>Settings</li>
      </ul>
    </div>
  </div>
  <div class="col-xs-8 col-sm-8 col-md-8 col-lg-8">
    <div class="card">
      <div class="row">
        <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12">
          <h1 class="card-head">Welcome to dashboard!! </h1>
          <p class="card-body">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ullam inventore vitae minus alias distinctio omnis iure nam quod ut. Dolores quasi consectetur alias illo quis, ab ipsam quos id rerum!</p>
          <p class="card-body">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ullam inventore vitae minus alias distinctio omnis iure nam quod ut. Dolores quasi consectetur alias illo quis, ab ipsam quos id rerum!</p>
        </div>
      </div>
    </div>
  </div>
  </div>
</template>

<style>
body{
  background-color:#f1f2f2;
}

.side-nav {
  text-decoration: none;
  height: 1000px;
  width: 40%;
  font-size: 1.3em;
  color: #264e86;
  background-color: rgba(0,0,0,0.2);
  font-family: 'Libre Baskerville', serif;
}

ul li {
  list-style-type: none;
  margin: 0;
  padding-left: 15px;
  padding-top: 70px;
}

.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.2s;
  width: 60%;
  margin-top: 130px;
  background-color: #fff;
  height: 400px;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.card-head {
  text-align: center;
  font-size: 2em;
  color: #264e86;
  padding-top: 15px;
  font-family: 'Libre Baskerville', serif;
}
.card-body {
  text-align: justify;
  font-size: 1.3em;
  color: #264e86;
  padding-top: 15px;
  font-family: 'Libre Baskerville', serif;
  margin-left: 15px;
  margin-right: 15px;
}
</style>

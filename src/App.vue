<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <h1>Find a Rock</h1>
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse">
          <p>Search</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <p>Add</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
  <footer>Link to Github: <a href='https://github.com/Tourtle21/creative-project-3'>Creative Project 3</a></footer>
</div>
</template>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;

}

#menu {
  box-sizing: border-box;
  display: flex;
  background: #B84901;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
}

#menu a {
  color: white;
  text-decoration: none;
}

#brand {
  display: flex;
  justify-content: center;
}
#brand h1 {
  text-decoration: none;
  color: white;
  border: none;
}

#brand img {
  height: 200px;
}
footer {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 50px;
  width: 100%;
  background: #B84901;
  color: white;
}
#side {
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}
</style>
<template>
  <div class="card-container">
    <div class="card">
      <div class="front">
        <div class="cover"></div>
        <div class="user">
          <img class="img-circle" alt="" :src="profile.photo" />
        </div>
        <div class="content">
          <div class="main">
            <h3 class="name">{{ profile.name }}</h3>
            <p class="profession">{{ profile.profession }}</p>
            <p class="text-center">{{ profile.motto }}</p>
          </div>
        </div>
      </div>`
    </div>
  </div>
</template>

<script>

/// https://github.com/vuejs/vue/issues/4638
/// vue will not support non standard syntax
const profile = {
  name: '',
  profession: '',
  motto: '',
  photo: ''
}

export default {
  props: {
    profile: {
      type: Object,
      default() {
        return { ...profile }
      }
    }
  }
};
</script>

<style>
.card-container {
  perspective: 800px;
  margin-bottom: 30px;
}

.card {
  transition: transform 0.5s;
  transform-style: preserve-3d;
  position: relative;
}

.front {
  backface-visibility: hidden;
  position: absolute;
  top: 0;
  left: 0;
  background-color: #fff;
  box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.14);
}

.front {
  z-index: 2;
}

.card {
  background: none repeat scroll 0 0 #ffffff;
  border-radius: 4px;
  color: #444444;
}
.card-container,
.front {
  width: 100%;
  height: 370px;
  border-radius: 4px;
}
.card .cover {
  height: 90px;
  overflow: hidden;
  border-radius: 4px 4px 0 0;
  background: #42b883;
}
.card .cover img {
  width: 100%;
  display: none;
}
.card .user {
  border-radius: 50%;
  display: block;
  height: 120px;
  margin: -55px auto 0;
  overflow: hidden;
  width: 120px;
}
.card .user img {
  background: none repeat scroll 0 0 #ffffff;
  border: 4px solid #ffffff;
  width: 100%;
}

.card .content {
  background-color: rgba(0, 0, 0, 0);
  box-shadow: none;
  padding: 10px 20px 20px;
}
.card .content .main {
  min-height: 160px;
}
.card .back .content .main {
  height: 215px;
}
.card .name {
  font-size: 20px;
  line-height: 28px;
  margin: 10px 0 0;
  text-align: center;
  text-transform: capitalize;
  font-weight: lighter;
}

.card .profession {
  color: #999999;
  text-align: center;
  margin-bottom: 20px;
}

.card .motto {
  border-bottom: 1px solid #eeeeee;
  color: #999999;
  font-size: 14px;
  font-weight: 400;
  padding-bottom: 10px;
  text-align: center;
} 
</style>
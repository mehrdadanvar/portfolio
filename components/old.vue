<template>
  <div>
    <div class="skills">
      <div class="cart">
        <h3>Responsive Design</h3>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Modi
          cupiditate sit aperiam laboriosam itaque dolores nisi provident animi,
          quidem exercitationem debitis qui minima voluptatem, temporibus eius?
          Architecto eligendi explicabo a?
        </p>
        <Icon
          name="carbon:logo-python"
          width="50"
          height="50"
          class="icon"
        ></Icon>
      </div>
      <div class="cart">
        <h3>The Bible</h3>
        <p>Html CSS Javascript</p>
        <Icon
          name="carbon:logo-python"
          width="48"
          height="48"
          class="icon"
        ></Icon>
      </div>
      <div class="cart">
        <h3>The Bible</h3>
        <p>Html CSS Javascript</p>
        <Icon
          name="carbon:logo-jupyter"
          width="48"
          height="48"
          class="icon"
        ></Icon>
      </div>
      <div class="cart">
        <h3>The Bible</h3>
        <p>Html CSS Javascript</p>
      </div>
      <Icon
        name="carbon:search"
        width="48"
        height="48"
        class="magnifier"
      ></Icon>
      <Icon
        name="ph:hand-fist-thin"
        width="48"
        height="48"
        class="test test1"
      ></Icon>
      <br />
    </div>
    <div class="art">
      <div class="user">
        <label for="">Maliciouu User</label>
        <Icon
          name="game-icons:pirate-skull"
          width="48"
          height="48"
          class="hit"
        ></Icon>
        <input
          type="text"
          placeholder="`SELECT * FROM Users; DROP TABLE Users;`"
          id="input"
          v-model="target"
        />
        <div class="btn">
          <button @click="animate">Kill thier Database</button>
          <Icon name="ph:airplane-tilt-fill" class="whobble"></Icon>
        </div>
      </div>
    </div>
  </div>
  
</template>

<script setup>
let target = ref("`SELECT * FROM Users; DROP TABLE Users;`");
function animate() {
  let text = target.value;
  let letters = [];
  for (let i = 0; i < text.length; i++) {
    letters.push(text[i]);
  }
  const timer = (ms) => new Promise((res) => setTimeout(res, ms));
  target.value = "";
  async function run() {
    for (let i = 0; i < letters.length; i++) {
      target.value = target.value.concat(letters[i]);
      console.log(target.value);
      console.log(letters[i]);
      await timer(50);
    }
  }
  run();
  hit.value = !hit.value;
}
let hit = ref(true);
</script>

<style scoped>
.magnifier {
  transform: rotate(80deg) translate(-1rem, -8.5rem);
  width: 5rem;
  height: 5rem;
  z-index: -1;
}

.hit {
  animation: hit 3s cubic-bezier(1, -0.85, 0.76, 1.57) infinite;
}
@keyframes hit {
  0% {
    transform: translate(10rem, 2rem);
  }
  100% {
    transform: translate(30rem);
  }
}
.whobble {
  animation: whobble 1s ease-in infinite;
}
@keyframes whobble {
  0% {
    transform: translate(0);
  }
  50% {
    transform: translate(0, 1rem);
  }
  100% {
    transform: translate(0);
  }
}
.btn {
  display: flex;
  flex-direction: column;
}
.user {
  display: flex;
  gap: 1rem;
  align-items: center;
}
.user > input {
  width: 20rem;
  height: 3rem;
  border-radius: 1rem;
  border: 1px solid grey;
  font-family: "Lato";
  padding-left: 1rem;
}
.art {
  margin: 2rem 2rem;
  padding: 1rem 1rem;
}
.test1 {
  transform: rotate(30deg, 30deg);
}
.test {
  color: #0097ff;
  width: 5rem;
  height: 5rem;
}
.test:hover {
  width: 10rem;
  height: 10rem;
}
.skills {
  display: flex;
  gap: 1rem;
}
.icon {
  color: rgb(48, 54, 54);
}
.cart {
  display: flex;
  border: 1px solid rgb(188, 188, 188);
  flex-direction: column;
  border-radius: 1rem;
  color: rgb(188, 188, 188);
  transition: 0.1s ease-out;
  max-width: 25rem;
}
.cart:hover {
  background-image: linear-gradient(
    to right bottom,
    #ff0091,
    #f013ab,
    #d92cc3,
    #ba41da,
    #8f52ed,
    #696ffb,
    #3d85ff,
    #0097ff,
    #00b5ff,
    #00d1ff,
    #00e9ff,
    #00ffef
  );
  color: white;
  transition: 0.1s ease-in;
  font-size: 18px;
  box-shadow: 0 0 40px grey;
  max-width: 26rem;
}
</style>

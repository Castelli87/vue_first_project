<!-- <script setup>
import { ref } from "vue";

const name = ref("Davide");
const isVisible = ref(true);
const status = ref("pending");
const placeLived = ref(["Belpasso", "Porcari City", "Elba", "Liverpool"]);
const link = ref("https://davidecastelli.tech/");

const newPlace = ref("");

const toogleStatus = () => {
  if (status.value === "active") {
    status.value = "pending";
  } else if (status.value === "pending") {
    status.value = "inactive";
  } else {
    status.value = "active";
  }
};

const addPlace = () => {
  if (newPlace.value.trim() !== "") {
    placeLived.value.push(newPlace.value);
    newPlace.value = "";
  }
};

const removePlace = (index) => {
  placeLived.value.splice(index, 1);
};
</script>
<template>
  <h1>Hello World from a Vue project</h1>
  <p v-if="isVisible">{{ name }}</p>

  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <form @submit.prevent="addPlace">
    <label for="newPlace">Add Place</label>
    <input type="text" id="newPlace" name="newPlace" v-model="newPlace" />
    <button type="submit">Submit</button>
  </form>

  <h3>Place where i lived</h3>
  <ul>
    <li v-for="(i, index) in placeLived" :key="i">
      <span>{{ i }}</span
      ><button @click="removePlace(index)">x</button>
    </li>
  </ul>

  <h3>My personal portfolio</h3>
  <a v-bind:href="link">Click to open from the long way</a>
  <div>
    <a :href="link">Click to open</a>
  </div>

  <br />

  <button v-on:click="toogleStatus">Change Status</button>
</template> -->


<script setup>
import { ref } from "vue";

const name = ref("Davide");
const isVisible = ref(true);
const status = ref("pending");
const placeLived = ref(["Belpasso",]);
const link = ref("https://davidecastelli.tech/");

const newPlace = ref("");

const toogleStatus = () => {
  if (status.value === "active") {
    status.value = "pending";
  } else if (status.value === "pending") {
    status.value = "inactive";
  } else {
    status.value = "active";
  }
};

const addPlace = () => {
  if (newPlace.value.trim() !== "") {
    placeLived.value.push(newPlace.value);
    newPlace.value = "";
  }
};

const removePlace = (index) => {
  placeLived.value.splice(index, 1);
};
</script>

<template>
  <div class="p-6 max-w-lg mx-auto bg-white rounded-xl shadow-md space-y-4">
    <h1 class="text-2xl font-bold text-gray-900">Hello World from a Vue project</h1>

    <p v-if="isVisible" class="text-lg text-gray-600">{{ name }}</p>

    <div class="text-gray-800">
      <p v-if="status === 'active'" class="text-green-600">User is active</p>
      <p v-else-if="status === 'pending'" class="text-yellow-600">User is pending</p>
      <p v-else class="text-red-600">User is inactive</p>
    </div>

    <form @submit.prevent="addPlace" class="space-y-2">
      <label for="newPlace" class="block text-gray-700">Add Place</label>
      <input
        type="text"
        id="newPlace"
        name="newPlace"
        v-model="newPlace"
        class="border border-gray-300 p-2 rounded w-full"
      />
      <button type="submit" class="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600">Submit</button>
    </form>

    <h3 class="text-xl font-semibold text-gray-800">Places where I've lived</h3>
    <ul class="list-disc pl-5 space-y-1">
      <li
        v-for="(i, index) in placeLived"
        :key="i"
        class="flex justify-between items-center"
      >
        <span>{{ i }}</span>
        <button @click="removePlace(index)" class="text-red-500 hover:text-red-700">x</button>
      </li>
    </ul>

    <h3 class="text-xl font-semibold text-gray-800">My personal portfolio</h3>
    <a
      v-bind:href="link"
      class="text-blue-500 hover:underline"
    >Click to open from the long way</a>

    <div>
      <a
        :href="link"
        class="text-blue-500 hover:underline"
      >Click to open</a>
    </div>

    <button
      v-on:click="toogleStatus"
      class="bg-green-500 text-white px-4 py-2 rounded hover:bg-green-600 mt-4"
    >
      Change Status
    </button>
  </div>
</template>

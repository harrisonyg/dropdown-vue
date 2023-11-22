<template>
  <div class="dropdown">
  <p>sort by </p>
  <div @click="toggleDropdown" class="cont ">
    <div >{{ selectedOption }}</div>
<svg xmlns="http://www.w3.org/2000/svg" width="12" height="6" viewBox="0 0 12 6" fill="none">
<path d="M0.837631 1.29554L5.50016 5.73872C5.55567 5.79146 5.6159 5.82884 5.68086 5.85085C5.74582 5.87321 5.81548 5.88459 5.88985 5.88497C5.96422 5.88535 6.03399 5.87469 6.09918 5.85299C6.16436 5.83164 6.22497 5.79488 6.28102 5.74272L11.0027 1.34752C11.1334 1.22579 11.1993 1.07313 11.2002 0.889546C11.2012 0.705958 11.1323 0.548241 10.9935 0.416394C10.8547 0.284546 10.6924 0.218147 10.5065 0.217196C10.3206 0.216246 10.1575 0.280981 10.0174 0.411403L5.89823 4.24579L1.81846 0.369481C1.68894 0.246424 1.52899 0.184408 1.33862 0.183434C1.14786 0.182459 0.982433 0.247182 0.842324 0.377603C0.702216 0.508025 0.631714 0.660658 0.63082 0.835504C0.629926 1.01035 0.698863 1.1637 0.837631 1.29554Z" fill="#262626"/>
</svg>
    </div>
    <ul v-if="isOpen" class="dropdown-list">
      <li v-for="option in options" :key="option" @click="selectOption(option)">
        {{ option }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const isOpen = ref(false);
const selectedOption = ref('Any');
const options = ref(['Option 1', 'Option 2', 'Option 3']);

const toggleDropdown = () => {
  isOpen.value = !isOpen.value;
};

const selectOption = (option) => {
  selectedOption.value = option;
  isOpen.value = false;
};
</script>

<style scoped>
.dropdown {
  position: relative;
}
.cont
{
    display: flex;
    align-items: center;
    gap: 2em;
}

.dropdown-list {
        list-style: none;
    padding: 0;
    margin: 0;
    position: absolute;
    top: 100%;
    left: 0;
    background-color: #fff;
    border: 1px solid #B6BAC3;
    border-radius: 0.5rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.dropdown-list li {
  padding: 8px;
  cursor: pointer;
}

.dropdown-list li:hover {
  background-color: #f0f0f0;
  border-radius:0.5em;
}
</style>

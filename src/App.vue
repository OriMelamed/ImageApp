<script setup>
import ImageGallery from './components/ImageGallery.vue';
import AddDetail from './components/AddDetail.vue';
import DetailCard from './components/DetailCard.vue';
import SideBar from './components/SideBar.vue';

import {ref} from 'vue'

const details =ref([
  {
    idNum:1,
    name: "Ori Melamed",
    email: "ori@gmail.com",
    phone: "123-123-123",
    assignee:'A',
    color: false
  },
  {
    idNum:2,
    name: "Michal Melamed",
    email: "melamed@gmail.com",
    phone: "111-222-333",
    assignee:'A',
    color: false
  },
  {
    idNum:3,
    name: "Anna Melamed",
    email: "melamed@gmail.com",
    phone: "111-222-333",
    assignee:'B',
    color: false
  },
  {
    idNum:4,
    name: "David Melamed",
    email: "melamed@gmail.com",
    phone: "111-222-333",
    assignee:'A',
    color: false
  }
])

const changeDetailsColorHandler = (id) => {
  details.value = details.value.map((person) => {
    if (person.id === id) {
      return { ...person, color: !person.color };
    }
    return person;
  });
};

const addDetailHandler = (person)=>{
      details.value.push(person);
    };

const deletePersonHandler = (id) =>{
  const index = details.value.findIndex(p => p.idNum === id);

  if (index !== -1) {
    details.value.splice(index, 1);
  }
}

const changeDetailListHandler = ()=>{}

</script>

<template>
  <VApp>
    <SideBar/>
    <VMain>
      {{ details.length == 0 ? "There are no details": null}}
      <v-row justify="center">
        <v-col
            v-for="d in details" 
            :key=d.idNum
            cols="5">
          
          <DetailCard 
          :key=d.idNum
          :person = d 
          @onClick = changeDetailsColorHandler
          @onDeletDetail = deletePersonHandler
          />  
        </v-col>
      </v-row>
        <AddDetail @addDetail=addDetailHandler />  
        <router-view/>
    </VMain>
  </VApp>
</template>

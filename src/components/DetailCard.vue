<script setup>
const props = defineProps(['person'])
const emit = defineEmits(['onClick','onDeletDetail'])

console.log(props.person.length)
 
</script>
<template>
    <v-container>
      <v-row align="center" justify="center">
        <v-col>
          <v-card
            class="mx-auto item-center"
            max-width="500">
            <v-card-item>
              <div>
              <v-btn @click="$emit('onDeletDetail',props.person.idNum)">
                X
              </v-btn>
              </div>
                <div class="text-overline mb-1">
                  {{ props.person.name }}
                </div>
                <div class="text-caption">{{ props.person.phone }}</div>
            </v-card-item>

            <v-card-actions>
              <v-btn @click="$emit('onClick',props.person.id)">
                {{ props.person.color ? "Hide" : "Show" }}
              </v-btn>
            </v-card-actions>
              <div class="text-h6 m-1" v-if="props.person.color">
                {{ props.person.email }}
              </div>
              
          </v-card>
        </v-col>
      </v-row>
    </v-container>
</template>
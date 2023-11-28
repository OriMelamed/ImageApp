<template>
      <VNavigationDrawer
        expand-on-hover
        rail
      >
        <v-list>
          <v-list-item
            prepend-avatar="https://randomuser.me/api/portraits/men/85.jpg"
            title="Ori Melamed"
            subtitle="ori.melamed@gmail.com"
          ></v-list-item>
        </v-list>

        <v-divider/>

        <v-list density="compact" nav>
          <v-list-item 
            prepend-icon="mdi-folder" 
            title="All users" 
            value="color"></v-list-item>
          <v-list-item 
            prepend-icon="mdi-account-multiple" 
            title="User A" 
            value="gray"></v-list-item>
            <v-list-item 
            prepend-icon="mdi-account-multiple" 
            title="User B" 
            value="gray1"></v-list-item>
         </v-list>
      </VNavigationDrawer>
</template>
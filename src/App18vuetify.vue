<template>
  <v-app>
    <v-btn color="success">success</v-btn>
    <v-btn color="error">error</v-btn>
    <v-btn color="warning">warning</v-btn>
    <v-btn color="info">info</v-btn>
<br>
    <div class="text-xs-center">
      <v-btn color="secondary">secondary</v-btn> &nbsp;
      <v-btn color="blue-grey">blue-grey</v-btn> &nbsp;
      <v-btn color="blue">blue</v-btn> &nbsp;
      <v-btn color="red">red</v-btn> &nbsp;
    </div>
    <br>
    <div>
        <v-btn icon="$vuetify" color="green">저장</v-btn> &nbsp;
        <v-btn icon="$vuetify" color="red">삭제</v-btn> &nbsp;
        <v-btn icon="$vuetify" color="blue">취소</v-btn> &nbsp;
    </div>

    <v-container>
    <v-row>
      <v-col cols="auto" justify="center">
        <v-btn density="compact" icon="mdi-plus"></v-btn>
      </v-col>

      <v-col cols="auto">
        <v-btn density="comfortable" icon="$vuetify"></v-btn>
      </v-col>

      <v-col cols="auto">
        <v-btn density="default" icon="mdi-open">new</v-btn>
      </v-col>
    </v-row>

  </v-container>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
}
</script>

<template>
  <v-app>
    
    <v-app-bar app dark>
      <v-spacer></v-spacer> <!--줄공백 유지-->
      <v-app-bar-title>
        <div :style="{fontSize:'24px'}">글쓰기 게시판 방명록</div>
      </v-app-bar-title>
    </v-app-bar>

    <v-main>
      <v-container>
        <v-row>
          <v-col cols="12" md="12">
            <v-btn  :style="{height:'50px', width:'120px'}"
            color="cyan">Home 홈화면</v-btn>
          </v-col>

          <v-col cols="12" md="10">
            <v-card>
              <v-form ref="form">
                <v-text-field
                  v-model="writer"
                  dense
                  outlined
                  label="작성자" 
                  style="width: 350px; margin-left: 100px; padding-top: 20px"
                  :rules="[(v) => !!v || '작성자는 필수입니다.']"
                ></v-text-field>
               <v-text-field
                  v-model="title"
                  dense
                  outlined
                  label="제목" value="bbb"
                  style="width: 350px; margin-left: 100px"
                  :rules="[(v) => !!v || '제목은 필수입니다.']"
                ></v-text-field>
                <v-textarea
                  v-model="text"
                  label="내용" value="ccc"
                  outlined
                  rows="5"
                  style="width: 400px; margin-left: 100px"
                  :rules="[(v) => !!v || '내용입력도 필수입니다.']"
                ></v-textarea>
                <v-file-input
                  class="input"
                  type="file"
                  counter
                  show-size
                  label="이미지 제출(여러개 가능)"
                  outlined
                  dense
                  multiple
                  prepend-icon="mdi-camera"
                  style="width: 400px; margin-left: 100px"
                />
                <v-img
                  v-for="(item, i) in uploadimageurl"
                  :key="i"
                  :src="item.url"
                  contain
                  height="150px"
                  width="200px"
                  style="border: 2px solid black; margin-left: 100px"
                />

                <v-btn
                  width="100px" color="green"
                  style="margin-left: 300px; margin-bottom: 30px"
                  type="submit"> 제 출 </v-btn>
                <v-btn
                  width="100px" color="green"
                  style="margin-left: 30px; margin-bottom: 30px"
                  @click="moveback"> 취 소 </v-btn>
              </v-form>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
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

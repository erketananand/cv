<template>
  <div class="col-md-12">
    <table class="table">
      <tbody>
        <tr>
          <td>
          </td>
          <td class="left-padding">
            <MyHeadline
              :name="name"
              :contact="contact"
            ></MyHeadline>
          </td>
        </tr>

        <tr>
          <td>
            <h5>Experience</h5>
          </td>
          <td class="text-left">
            <ul>
              <MyExperience
                v-for="(experience, index) in experiences"
                :experience="experience"
                :key="index"
              ></MyExperience>
            </ul>
          </td>
        </tr>

        <tr>
          <td>
            <h5>Skill</h5>
          </td>
          <td class="text-left">
            <ul>
              <MySkill
                v-for="(skl, index) in skill"
                :skill="skl"
                :key="index"
              ></MySkill>
            </ul>
          </td>
        </tr>

        <tr>
          <td>
            <h5>Tools</h5>
          </td>
          <td class="text-left">
            <ul>
              <MyTool
                v-for="(tool, index) in tools"
                :tool="tool"
                :key="index"
              ></MyTool>
            </ul>
          </td>
        </tr>

        <tr>
          <td>
            <h5>Education</h5>
          </td>
          <td class="text-left">
            <ul>
              <MyEducation
                v-for="(edu, index) in education"
                :edu="edu"
                :key="index"
              ></MyEducation>
            </ul>
          </td>
        </tr>

        <tr>
          <td>
            <h5>Social Media</h5>
          </td>
          <td class="text-left">
            <ul>
              <MySocialMedia
                v-for="(medium, index) in socialMedia"
                :medium="medium"
                :key="index"
              ></MySocialMedia>
            </ul>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script lang='ts'>
import Vue from 'vue';
import { Component } from 'vue-property-decorator';
import cvData from "../data/cv-data.json";
import MyEducation from "./my-education.vue";
import MyExperience from "./my-experience.vue";
import MyHeadline from "./my-headline.vue";
import MySocialMedia from "./my-social-media.vue";
import MySkill from "./my-skill.vue";
import MyTool from "./my-tool.vue";

@Component({
  components: {
    MyEducation,
    MyExperience,
    MyHeadline,
    MySocialMedia,
    MySkill,
    MyTool
  }
})
export default class Cv extends Vue {
  name!: string;
  contact!: any;
  experiences!: Array<any>;
  education!: Array<any>;
  skill!: Array<any>;
  socialMedia!: Array<any>;
  tools!: Array<any>;

  created() {
    this.name = cvData.name;
    this.contact = cvData.contact;
    this.experiences = cvData.experiences;
    this.education = cvData.education;
    this.skill = cvData.skill;
    this.tools = cvData.tools;
    this.socialMedia = cvData.socialMedia;
  }
}
</script>

<style scoped>
h1,
h2 {
  font-family: 'Cochin', 'Times New Roman';
  font-weight: normal;
}

table tr:first-child td {
  border-top: none;
}

td > ul > li:first-child {
  padding: 0;
}

td > ul > li {
  list-style-type: none;
  padding: 15px 0 0 0;
}

td.left-padding {
  clear: both;
  padding-left: 50px;
}

.circular-square {
  border-radius: 50%;
}
</style>

<template>
  <header>
    <div class="navbar navbar-dark shadow-sm"  style = "background-color: #259b24">
      <div class="container d-flex justify-content-between">
        <a class="navbar-brand d-flex align-items-center" href="#"
          ><i class="fa fa-camera"></i><strong>&#9993;CSMJU</strong></a
        >
      </div>
    </div>
  </header>
  <body style = "background-color: #a3e9a4;">
  <div class="container"  style = "background-color:#a3e9a4;">
    <div class="row mt-5">
      <div class="col-md-12 d-flex justify-content-center">
        <div class="card" style="width: 1200px; height 1200px">
          <div class="card-header">เขียนคำร้องทั่วไป</div>
          <div class="card-body">
            <form class="form">
              <div class="form-group">
                <label for="date">วันที่ Date:</label>
                <input
                  class="form-control"
                  type="date"
                  v-model="formData.date"
                  id="date"
                />
              </div>
              <div class="form-group">
                <label for="subject">รายวิชา Subject:</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.subject"
                  id="subject"
                />
              </div>
              <div class="form-group">
                <label for="to">ถึงอาจารย์ To:</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.to"
                  id="to"
                />
              </div>

              <div class="form-group">
                <label for="name">ชื่อนักศึกษา-นามสกุล Name-Lastname:</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.name"
                  id="name"
                />
              </div>
              <div class="form-group">
                <label for="studentID">รหัสนักศึกษา Student ID:</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.studentID"
                  id="studentID"
                />
              </div>

              <div class="form-group">
                <label for="major">สาขาวิชา Major:</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.major"
                  id="major"
                />
              </div>
              <div class="form-group">
                <label for="faculty">คณะ Faculty:</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.faculty"
                  id="faculty"
                />
              </div>
              <div class="form-group">
                <label for="telephone">เบอร์โทรศัพท์ Telephone:</label>
                <input
                  class="form-control"
                  type="text"
                  v-model="formData.telephone"
                  id="telephone"
                  maxlength="10"
                />
              </div>
              <div class="form-group">
                <label for="email">อีเมล Email:</label>
                <input
                  class="form-control"
                  type="email"
                  v-model="formData.email"
                  id="email"
                />
              </div>

              <div class="form-group">
                <label for="reason">คำร้อง Reason:</label>
                <textarea
                  class="form-control"
                  v-model="formData.reason"
                  id="reason"
                ></textarea>
              </div>

              <button
                type="submit"
                class="btn btn-primary"
                @click.prevent="submitForm"
              >
                Submit
              </button>
            </form>
          </div>
        </div>
      </div>
      <div class="col-md-8">
        <AccordionItems :formDataArray="formDataArray" />
      </div>
    </div>
  </div>
</body>
</template>

<script>
import AccordionItems from "./components/AccordionItems.vue";
export default {
  data() {
    return {
      formData: {
        date: null,
        subject: "",
        to: "",
        name: "",
        studentID: "",
        major: "",
        faculty: "",
        telephone: "",
        email: "",
        reason: "",
      },
      formDataArray: [],
    };
  },
  components: {
    AccordionItems,
  },
  methods: {
    submitForm() {
      // Add the form data to the formDataArray
      this.formDataArray.push(this.formData);

      // Reset the formData object
      this.formData = {
        date: null,
        subject: "",
        to: "",
        name: "",
        studentID: "",
        major: "",
        faculty: "",
        telephone: "",
        email: "",
        reason: "",
      };
    },
  },
};
</script>

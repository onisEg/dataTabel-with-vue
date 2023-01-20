<template>
  <div class="datatable">
    <div class="container my-1">
      <h1>datatable</h1>
      <table id="myTable" class="table table-striped mt-5">
        <thead>
          <tr>
            <th>user id</th>
            <th>id</th>
            <th>title</th>
            <th>body</th>
          </tr>
        </thead>

        <tfoot>
          <tr>
            <th>user id</th>
            <th>id</th>
            <th>title</th>
            <th>body</th>
          </tr>
        </tfoot>
      </table>
    </div>
  </div>
</template>

<script>
import $ from "jquery";

export default {
  name: "datatable",
  mounted() {
    this.getUsers();
  },
  methods: {
    getUsers() {
      fetch("https://jsonplaceholder.typicode.com/posts")
        .then((res) => {
          return res.json();
        })
        .then((response) => {
          console.log(response);
          $("#myTable").DataTable({
            data: response,
            columns: [
              { data: "userId" },
              { data: "id" },
              { data: "title" },
              { data: "body" },
            ],
          });
        })
        .catch((error) => {
          console.error(error.response);
        });
    },
  },
};
</script>

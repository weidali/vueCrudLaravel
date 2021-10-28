<template>
  <table class="table-auto">
    <thead>
      <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Adress</th>
        <th>Websit</th>
        <th>Actions</th>
      </tr>
    </thead>
    <tbody>
        <template v-for="item in comanies" :key="item.id">
            <tr>
                <td>{{ item.name }}</td>
                <td>{{ item.email }}</td>
                <td>{{ item.adress }}</td>
                <td>{{ item.website }}</td>
                <td><button @click="deleteCompany(item.id)">Delete</button></td>
            </tr>
        </template>
    </tbody>
  </table>
</template>

<script>
import useCompanies from "../../composable/companies";
import { onMounted } from "vue";

export default {
  setup() {
    const { comanies, getCompanies, destroyCompany } = useCompanies();

    onMounted(getCompanies);

    const deleteCompany = async (id) => {
      if (!window.confirm('Are you sure?')) {
        return;
      }
      await destroyCompany(id);
      await getCompanies();
    };

    return {
      comanies,
      destroyCompany,
    };
  },
};
</script>

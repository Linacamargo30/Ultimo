<template>
  <div class="container" id="vuejscrudapp">
    <div class="row">
      <div class="col-md-12 mt-5">
        <h1 class="text-center">QUICK SERVICES</h1>
        <hr />
      </div>
    </div>
    <div class="row">
      <div class="col-md-12">
        <!-- Agregar Registros-->
        <div>
          <b-button id="show-btn" @click="showModal('my-modal')"
            >Agregar Registros</b-button
          >

          <b-modal ref="my-modal" hide-footer title="Agregar Registros">
            <div>
              <form action="" @submit.prevent="onSubmit">
                <div class="form-group">
                  <label for="">Nombre</label>
                  <input type="text" v-model="firstname" class="form-control" />
                </div>
                <div class="form-group">
                  <label for="">Tipo doc</label>
                  <input
                    type="text"
                    v-model="type_document"
                    class="form-control"
                  />
                </div>
                <div class="form-group">
                  <label for="">Documento</label>
                  <input
                    type="number"
                    v-model="document"
                    class="form-control"
                  />
                </div>
                <div class="form-group">
                  <label for="">Correo</label>
                  <input type="email" v-model="email" class="form-control" />
                </div>
                <div class="form-group">
                  <label for="">Telefono</label>
                  <input type="number" v-model="phone" class="form-control" />
                </div>
                <div class="form-group">
                  <label for="">Direccion</label>
                  <input type="text" v-model="address" class="form-control" />
                </div>
                <div class="form-group">
                  <label for="">Ciudad</label>
                  <input type="text" v-model="city" class="form-control" />
                </div>
                <div class="form-group">
                  <button class="btn btn-sm btn-outline-info">
                    Agregar Registros
                  </button>
                </div>
              </form>
            </div>
            <b-button
              class="mt-3"
              variant="outline-danger"
              block
              @click="hideModal('my-modal')"
              >Cerrar</b-button
            >
          </b-modal>
        </div>

        <!-- Actualizar Registros -->
        <div>
          <b-modal ref="my-modal1" hide-footer title="Update Record">
            <div>
              <form action="" @submit.prevent="onUpdate">
                <div class="form-group">
                  <label for="">Nombre</label>
                  <input
                    type="text"
                    v-model="edit_firstname"
                    class="form-control"
                  />
                </div>
                <div class="form-group">
                  <label for="">Tipo doc</label>
                  <input
                    type="text"
                    v-model="edit_type_document"
                    class="form-control"
                  />
                </div>
                <div class="form-group">
                  <label for="">Documento</label>
                  <input
                    type="number"
                    v-model="edit_document"
                    class="form-control"
                  />
                </div>
                <div class="form-group">
                  <label for="">Correo</label>
                  <input
                    type="email"
                    v-model="edit_email"
                    class="form-control"
                  />
                </div>
                <div class="form-group">
                  <label for="">Telefono</label>
                  <input
                    type="number"
                    v-model="edit_phone"
                    class="form-control"
                  />
                </div>
                <div class="form-group">
                  <label for="">Direccion</label>
                  <input
                    type="text"
                    v-model="edit_address"
                    class="form-control"
                  />
                </div>
                <div class="form-group">
                  <label for="">Ciudad</label>
                  <input type="text" v-model="edit_city" class="form-control" />
                </div>
                <div class="form-group">
                  <button class="btn btn-sm btn-outline-info">
                    Actualizar Registros
                  </button>
                </div>
              </form>
            </div>
            <b-button
              class="mt-3"
              variant="outline-danger"
              block
              @click="hideModal('my-modal1')"
              >Cerrar</b-button
            >
          </b-modal>
        </div>
      </div>
    </div>

    <div class="row">
      <div class="col-md-12">
        <table class="table table-striped table-bordered" S>
          <thead>
            <tr>
              <th>Nombre</th>
              <th>Tipo doc</th>
              <th>Documento</th>
              <th>Correo</th>
              <th>Telefono</th>
              <th>Direccion</th>
              <th>Ciudad</th>
              <th>Estados</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(record, i) in records" :key="record.id">
              <td>{{ i + 1 }}</td>
              <td>{{ record.firstname }}</td>
              <td>{{ record.type_document }}</td>
              <td>{{ record.document }}</td>
              <td>{{ record.email }}</td>
              <td>{{ record.phone }}</td>
              <td>{{ record.address }}</td>
              <td>{{ record.city }}</td>
              <td>
                <button
                  @click="deleteRecord(record.id)"
                  class="btn btn-sm btn-outline-danger"
                >
                  Borrar
                </button>
                <button
                  @click="editRecord(record.id)"
                  class="btn btn-sm btn-outline-info"
                >
                  Edit
                </button>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

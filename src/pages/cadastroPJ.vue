<template>
  <q-page padding>
    <div class='q-title' align='center'> <q-btn round   absolute-top-left  color=primary icon='arrow_back' to='/clientes'></q-btn> CADASTRO DE EMPRESA</div>
    <div>
      <q-field icon="work">
        <q-input clearable v-model="objCliente[0].nomeEmpresaJ" float-label="Razão Social" />
      </q-field>
      <q-field icon="face">
        <q-input clearable v-model="objCliente[0].nomeClienteJ" float-label="Nome do responsável" />
      </q-field>
      <q-field icon="fingerprint">
        <q-input type='text' clearable v-model="objCliente[0].cnpjClienteJ" v-mask="'99.999.999/9999-99'" float-label="CNPJ" />
      </q-field>
      <q-field icon="place">
        <q-input type='textarea' clearable v-model="objCliente[0].enderecoClienteJ" float-label="Endereço do cliente" />
      </q-field>
      <q-field icon="phone">
        <q-input type='tel' v-model="objCliente[0].telefoneClienteJ" v-mask="'(99) 99999-9999'" float-label="Telefone" />
      </q-field>
      <q-field icon="alternate_email">
        <q-input type='email' clearable v-model="objCliente[0].emailClienteJ" float-label="E-mail" />
      </q-field>
      <q-field icon="description">
        <q-input type='textarea' clearable v-model="objCliente[0].obsClienteJ" float-label="Observações" />
      </q-field>
      <div align=center>
          <p><br><q-btn rounded color=primary icon='save' @click='salvarCliente' >Salvar</q-btn>
          <q-btn rounded color=primary icon='delete' @click='clearAll' >Limpar</q-btn>
              </p>         
          </div>
    </div>
    
  </q-page>
</template>

<script>
import AwesomeMask from "awesome-mask";
export default {
  data() {
    return {
      objCliente: [
        {
          tipo: "PJ",
          nomeEmpresaJ: "",
          nomeClienteJ: "",
          cnpjClienteJ: "",
          enderecoClienteJ: "",
          telefoneClienteJ: "",
          emailClienteJ: "",
          obsClienteJ: ""
        }
      ]
    };
  },
  methods: {
    clearAll() {
      (this.objCliente[0].nomeEmpresaJ = ""),
        (this.objCliente[0].nomeClienteJ = ""),
        (this.objCliente[0].cnpjClienteJ = ""),
        (this.objCliente[0].enderecoClienteJ = ""),
        (this.objCliente[0].telefoneClienteJ = ""),
        (this.objCliente[0].emailClienteJ = ""),
        (this.objCliente[0].obsClienteJ = "");
    },
    salvarCliente() {
      this.$clientes.push(this.objCliente[0]);
      console.log(this.objCliente[0]);
      console.log(this.$clientes);
      //   this.$q.localStorage.set(listaClientes, this.$clientes);
    }
  },
  directives: {
    mask: AwesomeMask
  }
};
</script>
<style>
</style>

<template>
    <div>
      <InventarioTable />
      <MovimientoInventarioTable />
      <ProductoOProveedor />
      <ProductoTable />
      <ProveedorTable />
      <ProyeccionConsumoTable />
    </div>
  </template>
  
  <script>
  import InventarioTable from './components/tables/InventarioTable.vue';
  import MovimientoInventarioTable from './components/tables/MovimientoInventarioTable.vue';
  import ProductoOProveedor from './components/tables/ProductoOProveedor.vue';
  import ProductoTable from './components/tables/ProductoTable.vue';
  import ProveedorTable from './components/tables/ProveedorTable.vue';
  import ProyeccionConsumoTable from './components/tables/ProyeccionConsumoTable.vue';
  
  export default {
    components: {
      InventarioTable,
      MovimientoInventarioTable,
      ProductoOProveedor,
      ProductoTable,
      ProveedorTable,
      ProyeccionConsumoTable
    }
  };
  </script>
  
<template src="../views/ProductoOProveedor.html"></template>


<script>
import "../assets/ProductoOProveedor.css";
export default {
    data() {
        return {
            searchQuery: "",
            selectedCategoria: "",
            productos: [
                { fecha: '2024-02-01', proveedor: 'Proveedor A', nombre: 'Laptop ASUS', categoria: 'Electrónicos', costo: '$800' },
                { fecha: '2024-02-05', proveedor: 'Proveedor B', nombre: 'Camiseta Nike', categoria: 'Ropa', costo: '$50' },
                { fecha: '2024-02-10', proveedor: 'Proveedor C', nombre: 'Smartphone Samsung', categoria: 'Electrónicos', costo: '$900' },
                { fecha: '2024-02-15', proveedor: 'Proveedor D', nombre: 'Pan Bimbo', categoria: 'Alimentos', costo: '$3' }
            ]
        };
    },
    computed: {
        filteredProductos() {
            let filtered = this.productos.filter(producto =>
                producto.nombre.toLowerCase().includes(this.searchQuery.toLowerCase()) ||
                producto.proveedor.toLowerCase().includes(this.searchQuery.toLowerCase())
            );
            if (this.selectedCategoria) {
                filtered = filtered.filter(p => p.categoria === this.selectedCategoria);
            }
            return filtered;
        }
    }
};
</script>

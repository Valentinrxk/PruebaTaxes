<template>
    <div class="layout-px-spacing">
        <div class="row layout-top-spacing" id="cancel-row">
            <div class="col-xl-12 col-lg-12 col-md-12">
                <div class="statbox panel box box-shadow">
                    <div class="panel-body">
                        <teleport to="#breadcrumb">
                            <ul class="navbar-nav flex-row">
                                <li>
                                    <div class="page-header">
                                        <nav class="breadcrumb-one" aria-label="breadcrumb">
                                            <ol class="breadcrumb">
                                                <li class="breadcrumb-item"><a href="javascript:;">Prueba técnica</a></li>
                                                <li class="breadcrumb-item active" aria-current="page"><span>Taxes Software</span></li>
                                            </ol>
                                        </nav>
                                    </div>
                                </li>
                            </ul>
                        </teleport>
                        <!--  -->
                        <h2 class="text-primary">Prueba técnica</h2>
                        <h5>Objetivos</h5>
                        <p>El objetivo principal de este test, es que la persona que lo realice se pueda familiarizar con Vue 3 y con el template que actualmente usamos en BlackTooth.</p>
                        <h5>Estándares a tener en cuenta</h5>
                        <p>Dentro del proyecto real de BT, en el lado del front tenemos estándarizados algunos aspectos que está bueno que se consideren y utilicen, tales como:</p>
                        <ul>
                            <li>Las peticiones asíncronas se realizan con Axios.</li>
                            <li>
                                El manejo de rutas se realiza con Vue Router, el cual se encuentra ya pre-configurado y ubicado dentro de la carpeta router. Al agregar nuevas rutas agregarlas en el
                                archivo index.js.
                            </li>
                            <li>El tipo de script que utilizamos dentro de un archivo .vue, es script setup.</li>
                            <li>
                                A la hora de crear una nueva vista, es crucial seguir con el mismo estilo del resto de la aplicación, para esto se puede consultar el template
                                <a href="https://demo.cork-vue3.sbthemes.com/" target="_blank" class="text-primary">haciendo click acá </a>
                            </li>
                            <li>Utilizamos boostrap 5 para los estilos.</li>
                            <li>Para los componentes globales, se utiliza la carpeta components, la cual se encuentra dentro de la carpeta src.</li>
                            <li>Los nombres de los archivos deben ser descriptivos y acordes a la nomenclatura utilizada en el resto del proyecto.</li>
                        </ul>
                        <h5>Instrucciones</h5>
                        <p>En el menú del costado de este proyecto, acceder a la opción tarea y luego entrar a la vista "Tabla"</p>
                        <p>Dentro, se encuentra el componente Prueba.vue, ubicado en la carpeta src/views/prueba/Prueba.vue</p>
                        <p>Puntos esenciales:</p>
                        <ul>
                            <li>Hacer una petición asíncrona al siguiente endpoint: "https://fakestoreapi.com/products?limit=10"</li>
                            <li>
                                Mostrar los datos en una tabla (ver tablas ya estiladas en página del template) iterando sobre el resultado de la API (utilizar v-for), con las siguientes columnas: id,
                                title, price, category, description, action (acá agregar un botón de "detalle" o "ver más")
                            </li>

                            <li>Agregar un mensaje o alert de bootstrap cuando la petición se está cargando, para indicarle al usuario que hay algo ejecutandose.</li>

                            <li>Si el precio del producto es mayor a 100, agregarle un color alternativo (utilizar clases de boostrap para cambiar el color y directiva condicional de Vue)</li>
                        </ul>
                        <p>Puntos extras:</p>
                        <ul>
                            <li>
                                Crear una vista/ruta adicional llamada /products/ para el detalle del producto, la misma deberá recibir un id dinámico. En el componente se deberá recuperar ese ID y
                                utilizarlo para hacer una llamada a la API, bajo este endpoint: "https://fakestoreapi.com/products/${acá iría el ID del producto}"
                            </li>
                            <li>En dicha vista, mostrar título, precio, descripción, calificación, stock, y foto del producto (hacer uso de cards de boostrap o algo similar)</li>
                            <li>
                                Modificar la tabla del punto escencial para que cuando se haga click en el botón de detalles o ver más, redireccione a la ruta /products/id, donde id es el ID del
                                producto clikeado.
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup></script>

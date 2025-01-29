<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Davi Express - Delivery en La Concordia</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        /* Estilos Generales */
        body {
            font-family: 'Roboto', sans-serif;
            background-color: #f4f4f4;
            color: #333;
            margin: 0;
            padding: 0;
        }

        /* Encabezado */
        header {
            background-color: #FF5722;
            color: white;
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: relative;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            flex-direction: column;
            text-align: center;
        }

        /* Foto de perfil centrada en el encabezado */
        .logo img {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            object-fit: cover;
            margin-top: 20px;
            margin-bottom: 10px;
        }

        /* Título centrado */
        .logo h1 {
            margin: 10px 0 0;
            font-size: 32px;
        }

        .logo p {
            font-size: 18px;
        }

        /* Menú de navegación */
        nav {
            display: flex;
            justify-content: flex-end;
            width: 100%;
        }

        nav ul {
            display: flex;
            list-style-type: none;
            padding: 0;
            margin: 0;
        }

        nav ul li {
            margin: 0 15px;
        }

        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: 700;
        }

        nav ul li a:hover {
            text-decoration: underline;
        }

        /* Botón de menú */
        #menu-button {
            display: none;
            flex-direction: column;
            cursor: pointer;
            position: absolute;
            top: 20px;
            right: 20px;
        }

        #menu-button div {
            background-color: white;
            height: 4px;
            width: 30px;
            margin: 5px 0;
        }

        /* Banner de bienvenida */
        #welcome-banner {
            background-color: #FF5722;
            color: white;
            text-align: center;
            padding: 50px 20px;
        }

        #welcome-banner h2 {
            font-size: 36px;
            margin-bottom: 10px;
        }

        #welcome-banner p {
            font-size: 18px;
            margin-bottom: 20px;
        }

        #welcome-banner input {
            padding: 10px;
            font-size: 16px;
            width: 300px;
            margin-right: 10px;
            border: none;
            border-radius: 5px;
        }

        #welcome-banner button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: white;
            color: #FF5722;
            border: none;
            cursor: pointer;
            border-radius: 5px;
            transition: background-color 0.3s ease;
        }

        #welcome-banner button:hover {
            background-color: #FF7043;
        }

        /* Categorías Populares */
        #categories {
            padding: 20px;
            background-color: #ffffff;
            text-align: center;
        }

        #categories h3 {
            margin-bottom: 20px;
        }

        #categories ul {
            display: flex;
            justify-content: center;
            list-style-type: none;
        }

        #categories ul li {
            margin: 0 15px;
            text-align: center;
        }

        #categories ul li a {
            color: #FF5722;
            text-decoration: none;
            font-weight: 700;
            font-size: 18px;
        }

        #categories ul li a:hover {
            text-decoration: underline;
        }

        #categories .category-item img {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            object-fit: cover;
            transition: transform 0.3s;
        }

        #categories .category-item img:hover {
            transform: scale(1.1);
        }

        /* WhatsApp botón flotante */
        #whatsapp-button {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: #25D366;
            color: white;
            border: none;
            border-radius: 50%;
            width: 60px;
            height: 60px;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            cursor: pointer;
            z-index: 1000;
        }

        #whatsapp-button img {
            width: 30px;
            height: 30px;
        }

        /* Footer */
        #footer {
            background-color: #333;
            color: white;
            padding: 20px;
            text-align: center;
        }

        #footer nav ul {
            display: flex;
            justify-content: center;
            list-style-type: none;
            padding: 0;
        }

        #footer nav ul li {
            margin: 0 10px;
        }

        #footer nav ul li a {
            color: white;
            text-decoration: none;
        }

        #footer nav ul li a:hover {
            text-decoration: underline;
        }

        /* Enlace Google Maps antes del pie de página */
        #google-map-link-footer {
            margin-top: 20px;
            background-color: #ffffff;
            color: #FF5722;
            font-weight: 700;
            padding: 10px;
            border-radius: 5px;
            text-decoration: none;
            display: inline-block;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            transition: background-color 0.3s;
        }

        #google-map-link-footer:hover {
            background-color: #FF7043;
            color: white;
        }

        /* Mapa de Google */
        #google-map {
            margin-top: 20px;
            text-align: center;
        }

        iframe {
            border: none;
            width: 100%;
            max-width: 600px;
            height: 450px;
        }

        /* Media Queries para móviles */
        @media (max-width: 768px) {
            /* Ajustes de menú */
            nav ul {
                display: none;
                flex-direction: column;
                align-items: center;
                width: 100%;
            }

            nav ul.show {
                display: flex;
            }

            #menu-button {
                display: flex;
            }

            #categories ul {
                flex-direction: column;
                align-items: center;
            }

            #categories ul li {
                margin: 10px 0;
            }
        }
    </style>
</head>
<body>

<!-- Página de inicio (Encabezado) -->
<header>
    <div class="logo">
        <img src="https://i.imgur.com/aVeB7EL.png" alt="Perfil">
        <h1>Davi Express</h1>
        <p>Delivery rápido y seguro en La Concordia</p>
    </div>

    <!-- Botón de menú (hamburguesa) -->
    <div id="menu-button" onclick="toggleMenu()">
        <div></div>
        <div></div>
        <div></div>
    </div>

    <!-- Menú de navegación -->
    <nav>
        <ul class="left">
            <li><a href="#">Contacto</a></li>
            <li><a href="#">Mi Cuenta</a></li>
            <li><a href="#cart">Carrito</a></li>
        </ul>
        <ul class="right">
            <li><a href="#">Inicio</a></li>
            <li><a href="#">Menú</a></li>
            <li><a href="#">Ofertas</a></li>
        </ul>
    </nav>
</header>

<!-- Banner de bienvenida -->
<section id="welcome-banner">
    <h2>¡Bienvenido a Davi Express!</h2>
    <p>¿Necesitas algo? ¡Nosotros te lo llevamos! Dentro y fuera de La Concordia.</p>
    <div>
        <input type="text" placeholder="Busca lo que necesites..." id="search">
        <button>Buscar</button>
    </div>
</section>

<!-- Categorías Populares -->
<section id="categories">
    <h3>Categorías Populares</h3>
    <ul>
        <li class="category-item">
            <a href="https://wa.me/593995302409?text=Hola,%20quiero%20pedir%20productos%20de%20la%20Tienda." target="_blank">
                <img src="https://i.imgur.com/gtwgPA2.png" alt="Tienda">
            </a>
            <a href="https://wa.me/593995302409?text=Hola,%20quiero%20pedir%20productos%20de%20la%20Tienda." target="_blank">Tienda</a>
        </li>
        <li class="category-item">
            <a href="https://wa.me/593995302409?text=Hola,%20necesito%20medicamentos%20de%20la%20Farmacia." target="_blank">
                <img src="https://i.imgur.com/2cth7mX.png" alt="Farmacias">
            </a>
            <a href="https://wa.me/593995302409?text=Hola,%20necesito%20medicamentos%20de%20la%20Farmacia." target="_blank">Farmacias</a>
        </li>
        <li class="category-item">
            <a href="https://wa.me/593995302409?text=Hola,%20quiero%20ordenar%20comida%20de%20Restaurantes." target="_blank">
                <img src="https://i.imgur.com/1Ndi0SM.png" alt="Restaurantes">
            </a>
            <a href="https://wa.me/593995302409?text=Hola,%20quiero%20ordenar%20comida%20de%20Restaurantes." target="_blank">Restaurantes</a>
        </li>
        <li class="category-item">
            <a href="https://wa.me/593995302409?text=Hola,%20quiero%20comprar%20bebidas%20de%20Licores." target="_blank">
                <img src="https://i.imgur.com/PY9JTLU.png" alt="Licores">
            </a>
            <a href="https://wa.me/593995302409?text=Hola,%20quiero%20comprar%20bebidas%20de%20Licores." target="_blank">Licores</a>
        </li>
    </ul>Siguenos en nuestras redes
</section>
<a href="https://www.facebook.com/profile.php?id=61572643046593" target="_blank">
<img src="https://i.imgur.com/NvHJqSL.png" alt="Facebook" style="width: 50px; height: 50px;"/>
</a><!-- WhatsApp botón flotante -->
<a id="whatsapp-button" href="https://wa.me/593995302409" target="_blank">
    <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp">
</a>

<!-- Mapa de Google con la ubicación de La Concordia -->
<section id="google-map">
    <h3>Ubicación de La Concordia</h3>
    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d31288.078845540707!2d-78.74301021485328!3d-0.058119388650922345!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x91d506f858f4b5ad%3A0xd417ab99bafc69c9!2sLa%20Concordia%2C%20Ecuador!5e0!3m2!1ses-419!2sus!4v1674927033030!5m2!1ses-419!2sus" 
            width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
</section>

<!-- Pie de página -->
<section id="footer">
    <p>© 2025 Davi Express. Todos los derechos reservados.</p>
    <nav>
        <ul>
            <li><a href="#">Política de Privacidad</a></li>
            <li><a href="#">Términos y Condiciones</a></li>
            <li><a href="#">Ayuda</a></li>
        </ul>
    </nav>
</section>

<script>
    function toggleMenu() {
menu.classList.toggle('show');
    }
</script>

</body>
</html>

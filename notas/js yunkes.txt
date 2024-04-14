// Capturar el formulario de búsqueda
const formBusqueda = document.getElementById('form-busqueda');

// Manejar el envío del formulario
formBusqueda.addEventListener('submit', function(event) {
    event.preventDefault(); // Evitar que se envíe el formulario

    // Limpiar el formulario
    formBusqueda.reset();

    // Ocultar la imagen del mapa de Sonora
    document.getElementById('mapa').style.display = 'none';

    // Ejemplo de resultados simulados para un Nissan March 2010 en Hermosillo
    const resultadosHTML = `
        <div class="yunkes">
            <h2>Yunke "Los Hermanos"</h2>
            <div class="info">
                <p>Dirección: Lázaro Cárdenas 1, Hermosillo, Sonora</p>
                <p>Teléfono: +52 6622-29-38-79</p>
                <p>WhatsApp: <a href="https://wa.me/+526622293879">6622-29-38-79</a></p>
            </div>
            <img src="ejemploxd.jpg" alt="Ejemplo XD" class="yunkes-img-search">
        </div>
        <div class="yunkes">
            <h2>Yunke "Don Felix"</h2>
            <div class="info">
                <p>Dirección: Veracrúz 56, Hermosillo, Sonora</p>
                <p>Teléfono: +52 6621-82-97-24</p>
                <p>WhatsApp: <a href="https://wa.me/+526621829724">6621-82-97-24</a></p>
            </div>
            <img src="ejemploxp.jpg" alt="Ejemplo XP" class="yunkes-img-search">
        </div>
    `;

    // Mostrar los resultados en #resultados
    const resultadosElement = document.getElementById('resultados');
    resultadosElement.innerHTML = resultadosHTML;

    // Ocultar las imágenes de ejemplo1, ejemplo2 y ejemplo3
    const imagenesEjemplo = document.querySelectorAll('.yunkes-img');
    imagenesEjemplo.forEach(function(imagen) {
        if (imagen.src.includes('ejemplo1.jpg') || imagen.src.includes('ejemplo2.jpg') || imagen.src.includes('ejemplo3.jpg')) {
            imagen.style.display = 'none';
        }
    });

    // Mostrar la sección de resultados
    resultadosElement.classList.remove('hidden');
});

// Capturar el logo
const logo = document.getElementById('logo');

// Manejar el clic en el logo
logo.addEventListener('click', function() {
    window.location.reload();
});

// Capturar el ícono de ubicación
const locationIcon = document.getElementById('location-icon');

// Capturar la sección de resultados
const resultados = document.getElementById('resultados');

// Manejar el clic en el ícono de ubicación
locationIcon.addEventListener('click', function() {
    // Si los resultados están ocultos, los muestra; de lo contrario, los oculta
    resultados.classList.toggle('hidden');
});

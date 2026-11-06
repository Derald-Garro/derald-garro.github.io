
Landing Page Moderna - Nova

Esta es la documentación y estructura para la landing page desarrollada en HTML y Tailwind CSS.

🛠️ Tecnologías Utilizadas

HTML5: Estructura semántica de la página.

Tailwind CSS (via CDN): Framework de utilidades CSS para diseño responsive y estilos modernos.

Font Awesome: Colección de iconos vectoriales.

Google Fonts (Inter): Tipografía moderna y de fácil lectura.

JavaScript Plain (ES6): Para interactividad en menú móvil y lógica de simulación de formulario.

🎨 Características del Diseño

Navegación Adaptativa (Responsive Navbar):

Menú colapsable automático en dispositivos móviles.

Navegación suave (smooth scroll) al hacer clic en las secciones.

Sección Principal (Hero Section):

Título principal llamativo con degradados de color.

Botones de llamada a la acción (CTA).

Indicadores clave (métricas de la empresa).

Sección de Servicios (Grid Interactivo):

Tarjetas con efectos dinámicos en hover (transition, scale).

Sección de Contacto (Formulario):

Formulario interactivo con retroalimentación visual al enviar el mensaje.

Información de contacto clara e iconos integrados.
<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nova - Soluciones Digitales Modernas</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Font Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            50: '#f0f7ff',
                            100: '#e0effe',
                            500: '#3b82f6',
                            600: '#2563eb',
                            700: '#1d4ed8',
                            900: '#1e3a8a',
                        }
                    }
                }
            }
        }
    </script>
</head>
<body class="bg-slate-50 text-slate-800 font-sans antialiased selection:bg-brand-500 selection:text-white flex flex-col min-h-screen">

    <!-- Navegación -->
    <header class="sticky top-0 z-50 backdrop-blur-md bg-white/80 border-b border-slate-100 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <!-- Logo -->
                <div class="flex-shrink-0 flex items-center gap-2 cursor-pointer" onclick="window.scrollTo({top: 0, behavior: 'smooth'})">
                    <div class="w-9 h-9 rounded-xl bg-gradient-to-tr from-brand-600 to-indigo-500 flex items-center justify-center text-white shadow-md shadow-brand-500/20">
                        <i class="fa-solid fa-bolt text-lg"></i>
                    </div>
                    <span class="font-bold text-xl tracking-tight text-slate-900">Nova<span class="text-brand-600">.</span></span>
                </div>

                <!-- Menú Escritorio -->
                <nav class="hidden md:flex items-center space-x-8 font-medium text-slate-600">
                    <a href="#inicio" class="hover:text-brand-600 transition-colors">Inicio</a>
                    <a href="#servicios" class="hover:text-brand-600 transition-colors">Servicios</a>
                    <a href="#contacto" class="hover:text-brand-600 transition-colors">Contacto</a>
                </nav>

                <!-- Botón CTA Escritorio -->
                <div class="hidden md:flex items-center">
                    <a href="#contacto" class="bg-slate-900 hover:bg-brand-600 text-white px-5 py-2.5 rounded-xl font-medium text-sm transition-all duration-300 shadow-sm hover:shadow-lg hover:shadow-brand-500/25">
                        Empezar ahora
                    </a>
                </div>

                <!-- Botón Menú Móvil -->
                <div class="md:hidden">
                    <button id="mobile-menu-btn" type="button" class="text-slate-600 hover:text-slate-900 focus:outline-none p-2 rounded-lg" aria-label="Abrir menú">
                        <i id="menu-icon-open" class="fa-solid fa-bars text-xl"></i>
                        <i id="menu-icon-close" class="fa-solid fa-xmark text-xl hidden"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Menú Desplegable Móvil -->
        <div id="mobile-menu" class="hidden md:hidden bg-white border-b border-slate-100 px-4 pt-2 pb-6 space-y-3 shadow-lg">
            <a href="#inicio" class="mobile-link block px-3 py-2 rounded-lg text-base font-medium text-slate-700 hover:bg-slate-50 hover:text-brand-600">Inicio</a>
            <a href="#servicios" class="mobile-link block px-3 py-2 rounded-lg text-base font-medium text-slate-700 hover:bg-slate-50 hover:text-brand-600">Servicios</a>
            <a href="#contacto" class="mobile-link block px-3 py-2 rounded-lg text-base font-medium text-slate-700 hover:bg-slate-50 hover:text-brand-600">Contacto</a>
            <a href="#contacto" class="mobile-link block w-full text-center bg-brand-600 text-white font-medium py-3 rounded-xl shadow-md">Empezar ahora</a>
        </div>
    </header>

    <main class="flex-grow">
        <!-- Sección Hero -->
        <section id="inicio" class="relative overflow-hidden pt-12 pb-20 lg:pt-24 lg:pb-32">
            <div class="absolute inset-0 -z-10 bg-[radial-gradient(45rem_50rem_at_top,theme(colors.brand.100),theme(colors.slate.50))] opacity-60"></div>
            
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center max-w-3xl mx-auto">
                    <!-- Badge destacado -->
                    <div class="inline-flex items-center gap-2 px-3 py-1.5 rounded-full bg-brand-50 border border-brand-100 text-brand-700 text-xs sm:text-sm font-semibold mb-6 animate-pulse">
                        <span class="w-2 h-2 rounded-full bg-brand-600"></span>
                        Innovación digital a tu alcance
                    </div>
                    
                    <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold text-slate-900 tracking-tight leading-[1.15]">
                        Transformamos tus ideas en <span class="bg-gradient-to-r from-brand-600 to-indigo-600 bg-clip-text text-transparent">experiencias digitales</span>
                    </h1>
                    
                    <p class="mt-6 text-lg sm:text-xl text-slate-600 leading-relaxed font-normal">
                        Diseñamos y desarrollamos soluciones web a la medida de tu negocio. Aumenta tus ventas y optimiza tu presencia digital hoy mismo.
                    </p>

                    <div class="mt-10 flex flex-col sm:flex-row items-center justify-center gap-4">
                        <a href="#contacto" class="w-full sm:w-auto bg-brand-600 hover:bg-brand-700 text-white font-semibold px-8 py-4 rounded-xl shadow-lg shadow-brand-500/30 hover:shadow-xl hover:shadow-brand-500/40 transition-all duration-300 flex items-center justify-center gap-2">
                            <span>Solicitar propuesta</span>
                            <i class="fa-solid fa-arrow-right text-sm"></i>
                        </a>
                        <a href="#servicios" class="w-full sm:w-auto bg-white hover:bg-slate-100 text-slate-700 font-semibold px-8 py-4 rounded-xl border border-slate-200 shadow-sm transition-all duration-300 flex items-center justify-center">
                            Explorar servicios
                        </a>
                    </div>

                    <!-- Métricas breves -->
                    <div class="mt-16 grid grid-cols-2 md:grid-cols-3 gap-6 pt-10 border-t border-slate-200/80">
                        <div>
                            <p class="text-3xl font-extrabold text-slate-900">+150</p>
                            <p class="text-sm font-medium text-slate-500 mt-1">Proyectos Entregados</p>
                        </div>
                        <div>
                            <p class="text-3xl font-extrabold text-slate-900">99%</p>
                            <p class="text-sm font-medium text-slate-500 mt-1">Clientes Satisfechos</p>
                        </div>
                        <div class="col-span-2 md:col-span-1">
                            <p class="text-3xl font-extrabold text-slate-900">24/7</p>
                            <p class="text-sm font-medium text-slate-500 mt-1">Soporte Técnico</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Sección Características / Servicios -->
        <section id="servicios" class="py-20 bg-white border-y border-slate-100">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center max-w-2xl mx-auto mb-16">
                    <h2 class="text-xs sm:text-sm font-bold uppercase tracking-widest text-brand-600">Lo que ofrecemos</h2>
                    <p class="mt-2 text-3xl sm:text-4xl font-bold text-slate-900">Nuestros Servicios Destacados</p>
                    <p class="mt-4 text-slate-600">Ofrecemos un enfoque integral para garantizar el éxito y crecimiento constante de tu marca.</p>
                </div>

                <!-- Grid de Tarjetas Interactivas -->
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                    
                    <!-- Tarjeta 1 -->
                    <div class="group relative bg-slate-50 p-8 rounded-2xl border border-slate-100 hover:border-brand-200 hover:bg-white hover:shadow-xl transition-all duration-300 flex flex-col justify-between">
                        <div>
                            <div class="w-14 h-14 rounded-xl bg-brand-100 text-brand-600 flex items-center justify-center text-2xl mb-6 group-hover:scale-110 group-hover:bg-brand-600 group-hover:text-white transition-all duration-300">
                                <i class="fa-solid fa-code"></i>
                            </div>
                            <h3 class="text-xl font-bold text-slate-900 mb-3 group-hover:text-brand-600 transition-colors">Desarrollo Web</h3>
                            <p class="text-slate-600 text-sm leading-relaxed">
                                Sitios rápidos, adaptables y optimizados para buscadores. Creamos aplicaciones web modernas adaptadas a tus necesidades.
                            </p>
                        </div>
                        <div class="mt-6 pt-4 border-t border-slate-200/60 flex items-center text-xs font-semibold text-brand-600 group-hover:translate-x-1 transition-transform">
                            <span>Saber más</span>
                            <i class="fa-solid fa-chevron-right ml-1"></i>
                        </div>
                    </div>

                    <!-- Tarjeta 2 -->
                    <div class="group relative bg-slate-50 p-8 rounded-2xl border border-slate-100 hover:border-brand-200 hover:bg-white hover:shadow-xl transition-all duration-300 flex flex-col justify-between">
                        <div>
                            <div class="w-14 h-14 rounded-xl bg-indigo-100 text-indigo-600 flex items-center justify-center text-2xl mb-6 group-hover:scale-110 group-hover:bg-indigo-600 group-hover:text-white transition-all duration-300">
                                <i class="fa-solid fa-pen-ruler"></i>
                            </div>
                            <h3 class="text-xl font-bold text-slate-900 mb-3 group-hover:text-indigo-600 transition-colors">Diseño UI/UX</h3>
                            <p class="text-slate-600 text-sm leading-relaxed">
                                Interfaces intuitivas y atractivas orientadas a la mejor experiencia del usuario para maximizar la retención y conversión.
                            </p>
                        </div>
                        <div class="mt-6 pt-4 border-t border-slate-200/60 flex items-center text-xs font-semibold text-indigo-600 group-hover:translate-x-1 transition-transform">
                            <span>Saber más</span>
                            <i class="fa-solid fa-chevron-right ml-1"></i>
                        </div>
                    </div>

                    <!-- Tarjeta 3 -->
                    <div class="group relative bg-slate-50 p-8 rounded-2xl border border-slate-100 hover:border-brand-200 hover:bg-white hover:shadow-xl transition-all duration-300 flex flex-col justify-between">
                        <div>
                            <div class="w-14 h-14 rounded-xl bg-emerald-100 text-emerald-600 flex items-center justify-center text-2xl mb-6 group-hover:scale-110 group-hover:bg-emerald-600 group-hover:text-white transition-all duration-300">
                                <i class="fa-solid fa-chart-line"></i>
                            </div>
                            <h3 class="text-xl font-bold text-slate-900 mb-3 group-hover:text-emerald-600 transition-colors">Marketing Digital</h3>
                            <p class="text-slate-600 text-sm leading-relaxed">
                                Estrategias efectivas de posicionamiento SEO y campañas para atraer tráfico cualificado y clientes potenciales a tu web.
                            </p>
                        </div>
                        <div class="mt-6 pt-4 border-t border-slate-200/60 flex items-center text-xs font-semibold text-emerald-600 group-hover:translate-x-1 transition-transform">
                            <span>Saber más</span>
                            <i class="fa-solid fa-chevron-right ml-1"></i>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <!-- Sección Formulario de Contacto -->
        <section id="contacto" class="py-20 bg-slate-50">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="max-w-4xl mx-auto bg-white rounded-3xl shadow-xl overflow-hidden border border-slate-100">
                    <div class="grid grid-cols-1 md:grid-cols-5">
                        
                        <!-- Info Lateral -->
                        <div class="md:col-span-2 bg-slate-900 text-white p-8 sm:p-10 flex flex-col justify-between">
                            <div>
                                <h3 class="text-2xl font-bold mb-4">¡Hablemos de tu proyecto!</h3>
                                <p class="text-slate-400 text-sm mb-8">Déjanos tu mensaje y nuestro equipo se pondrá en contacto contigo en menos de 24 horas.</p>
                                
                                <div class="space-y-6 text-sm">
                                    <div class="flex items-center gap-4">
                                        <div class="w-10 h-10 rounded-lg bg-slate-800 flex items-center justify-center text-brand-500">
                                            <i class="fa-solid fa-envelope"></i>
                                        </div>
                                        <span>contacto@ejemplo.com</span>
                                    </div>
                                    <div class="flex items-center gap-4">
                                        <div class="w-10 h-10 rounded-lg bg-slate-800 flex items-center justify-center text-brand-500">
                                            <i class="fa-solid fa-phone"></i>
                                        </div>
                                        <span>+506 8000 0000</span>
                                    </div>
                                    <div class="flex items-center gap-4">
                                        <div class="w-10 h-10 rounded-lg bg-slate-800 flex items-center justify-center text-brand-500">
                                            <i class="fa-solid fa-location-dot"></i>
                                        </div>
                                        <span>San José, Costa Rica</span>
                                    </div>
                                </div>
                            </div>

                            <div class="mt-12 flex gap-4 text-slate-400">
                                <a href="#" class="hover:text-white transition-colors"><i class="fa-brands fa-twitter text-lg"></i></a>
                                <a href="#" class="hover:text-white transition-colors"><i class="fa-brands fa-linkedin text-lg"></i></a>
                                <a href="#" class="hover:text-white transition-colors"><i class="fa-brands fa-github text-lg"></i></a>
                            </div>
                        </div>

                        <!-- Formulario Frontend -->
                        <div class="md:col-span-3 p-8 sm:p-10">
                            <!-- Alerta de éxito -->
                            <div id="alert-success" class="hidden mb-6 p-4 rounded-xl bg-emerald-50 border border-emerald-200 text-emerald-700 text-sm flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-lg"></i>
                                <span>¡Mensaje enviado con éxito! Nos pondremos en contacto pronto.</span>
                            </div>

                            <form id="contact-form" onsubmit="handleFormSubmit(event)" class="space-y-5">
                                <div>
                                    <label for="name" class="block text-xs font-semibold uppercase text-slate-600 mb-2">Nombre completo</label>
                                    <input type="text" id="name" required placeholder="Tu nombre" 
                                        class="w-full px-4 py-3 rounded-xl border border-slate-200 focus:outline-none focus:ring-2 focus:ring-brand-500 focus:border-transparent transition-all text-sm">
                                </div>

                                <div>
                                    <label for="email" class="block text-xs font-semibold uppercase text-slate-600 mb-2">Correo electrónico</label>
                                    <input type="email" id="email" required placeholder="tu@correo.com" 
                                        class="w-full px-4 py-3 rounded-xl border border-slate-200 focus:outline-none focus:ring-2 focus:ring-brand-500 focus:border-transparent transition-all text-sm">
                                </div>

                                <div>
                                    <label for="message" class="block text-xs font-semibold uppercase text-slate-600 mb-2">Mensaje</label>
                                    <textarea id="message" rows="4" required placeholder="¿En qué podemos ayudarte?" 
                                        class="w-full px-4 py-3 rounded-xl border border-slate-200 focus:outline-none focus:ring-2 focus:ring-brand-500 focus:border-transparent transition-all text-sm resize-none"></textarea>
                                </div>

                                <button type="submit" id="submit-btn" 
                                    class="w-full bg-brand-600 hover:bg-brand-700 text-white font-semibold py-3.5 px-6 rounded-xl shadow-lg shadow-brand-500/25 transition-all duration-300 flex items-center justify-center gap-2">
                                    <span>Enviar mensaje</span>
                                    <i class="fa-solid fa-paper-plane text-xs"></i>
                                </button>
                            </form>
                        </div>

                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Pie de página -->
    <footer class="bg-slate-900 text-slate-400 py-8 border-t border-slate-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col sm:flex-row items-center justify-between gap-4">
            <div class="flex items-center gap-2">
                <div class="w-7 h-7 rounded-lg bg-brand-600 flex items-center justify-center text-white text-xs font-bold">
                    <i class="fa-solid fa-bolt"></i>
                </div>
                <span class="font-bold text-white tracking-tight">Nova.</span>
            </div>
            <p class="text-xs text-center sm:text-right">&copy; <span id="year"></span> Nova Inc. Todos los derechos reservados.</p>
        </div>
    </footer>

    <!-- JavaScript Interactivo -->
    <script>
        // Ajustar el año actual automáticamente en el footer
        document.getElementById('year').textContent = new Date().getFullYear();

        // Control del Menú Móvil
        const menuBtn = document.getElementById('mobile-menu-btn');
        const mobileMenu = document.getElementById('mobile-menu');
        const menuIconOpen = document.getElementById('menu-icon-open');
        const menuIconClose = document.getElementById('menu-icon-close');
        const mobileLinks = document.querySelectorAll('.mobile-link');

        function toggleMenu() {
            const isMenuOpen = !mobileMenu.classList.contains('hidden');
            if (isMenuOpen) {
                mobileMenu.classList.add('hidden');
                menuIconOpen.classList.remove('hidden');
                menuIconClose.classList.add('hidden');
            } else {
                mobileMenu.classList.remove('hidden');
                menuIconOpen.classList.add('hidden');
                menuIconClose.classList.remove('hidden');
            }
        }

        menuBtn.addEventListener('click', toggleMenu);

        // Cerrar menú al hacer clic en cualquier enlace en móvil
        mobileLinks.forEach(link => {
            link.addEventListener('click', () => {
                if (!mobileMenu.classList.contains('hidden')) {
                    toggleMenu();
                }
            });
        });

        // Simulación de envío de formulario de contacto
        function handleFormSubmit(event) {
            event.preventDefault();

            const submitBtn = document.getElementById('submit-btn');
            const alertSuccess = document.getElementById('alert-success');
            const form = document.getElementById('contact-form');

            // Feedback de envío
            submitBtn.disabled = true;
            submitBtn.innerHTML = '<i class="fa-solid fa-spinner animate-spin"></i> <span>Enviando...</span>';

            setTimeout(() => {
                // Restablecer botón y mostrar alerta
                submitBtn.disabled = false;
                submitBtn.innerHTML = '<span>Enviar mensaje</span> <i class="fa-solid fa-paper-plane text-xs"></i>';
                
                alertSuccess.classList.remove('hidden');
                form.reset();

                // Ocultar la alerta de éxito tras 5 segundos
                setTimeout(() => {
                    alertSuccess.classList.add('hidden');
                }, 5000);
            }, 1200);
        }
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Publicar App Rappi en Netlify</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #00b8a9, #ff8c00);
            color: #333;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1000px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            overflow: hidden;
        }
        
        header {
            background: #00b8a9;
            color: white;
            padding: 30px;
            text-align: center;
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
        }
        
        .subtitle {
            font-size: 1.2rem;
            opacity: 0.9;
        }
        
        .content {
            padding: 30px;
        }
        
        .step {
            display: flex;
            margin-bottom: 30px;
            background: #f8f9fa;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }
        
        .step-number {
            background: #ff8c00;
            color: white;
            font-size: 2rem;
            font-weight: bold;
            width: 80px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .step-content {
            padding: 20px;
            flex: 1;
        }
        
        .step-title {
            font-size: 1.3rem;
            font-weight: bold;
            margin-bottom: 10px;
            color: #00b8a9;
        }
        
        .code-block {
            background: #2d2d2d;
            color: #f8f8f2;
            padding: 15px;
            border-radius: 5px;
            margin: 10px 0;
            font-family: monospace;
            overflow-x: auto;
        }
        
        .action-buttons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
            flex-wrap: wrap;
        }
        
        .btn {
            padding: 12px 20px;
            border: none;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s ease;
        }
        
        .btn-primary {
            background: #00b8a9;
            color: white;
        }
        
        .btn-secondary {
            background: #ff8c00;
            color: white;
        }
        
        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .demo-area {
            background: #e8f4f3;
            padding: 20px;
            border-radius: 10px;
            margin-top: 30px;
            text-align: center;
        }
        
        .demo-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: #00b8a9;
        }
        
        .app-preview {
            background: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            max-width: 400px;
            margin: 0 auto;
        }
        
        .app-header {
            background: #00b8a9;
            color: white;
            padding: 15px;
            border-radius: 10px 10px 0 0;
            display: flex;
            justify-content: space-between;
        }
        
        .app-content {
            padding: 15px;
        }
        
        .restaurant-card {
            background: white;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 15px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .restaurant-image {
            width: 60px;
            height: 60px;
            border-radius: 10px;
            background: #ff8c00;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
        }
        
        .restaurant-info {
            flex: 1;
        }
        
        .restaurant-name {
            font-weight: bold;
            margin-bottom: 5px;
        }
        
        .restaurant-details {
            font-size: 0.9rem;
            color: #666;
        }
        
        footer {
            text-align: center;
            padding: 20px;
            background: #f8f9fa;
            color: #666;
            margin-top: 30px;
        }
        
        .success-message {
            background: #4caf50;
            color: white;
            padding: 15px;
            border-radius: 10px;
            margin-top: 20px;
            display: none;
        }
        
        @media (max-width: 768px) {
            .step {
                flex-direction: column;
            }
            
            .step-number {
                width: 100%;
                height: 60px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1><i class="fas fa-rocket"></i> Publica tu App Rappi en Netlify</h1>
            <p class="subtitle">En 5 minutos y completamente GRATIS</p>
        </header>
        
        <div class="content">
            <div class="step">
                <div class="step-number">1</div>
                <div class="step-content">
                    <div class="step-title">Prepara tu archivo HTML</div>
                    <p>Guarda tu código en un archivo llamado <strong>index.html</strong>. Asegúrate de que todo el código esté en un solo archivo o que los archivos CSS/JS estén en la misma carpeta.</p>
                    <div class="action-buttons">
                        <button class="btn btn-primary" onclick="downloadApp()">
                            <i class="fas fa-download"></i> Descargar App Rappi lista
                        </button>
                    </div>
                </div>
            </div>
            
            <div class="step">
                <div class="step-number">2</div>
                <div class="step-content">
                    <div class="step-title">Ve a Netlify</div>
                    <p>Abre <a href="https://netlify.com" target="_blank">netlify.com</a> y crea una cuenta gratis (puedes registrarte con Google o GitHub).</p>
                    <div class="action-buttons">
                        <a href="https://app.netlify.com/signup" class="btn btn-primary" target="_blank">
                            <i class="fas fa-external-link-alt"></i> Ir a Netlify
                        </a>
                    </div>
                </div>
            </div>
            
            <div class="step">
                <div class="step-number">3</div>
                <div class="step-content">
                    <div class="step-title">Despliega tu app</div>
                    <p>En el dashboard de Netlify, busca la sección "Drag and drop your site output folder here" y arrastra la carpeta que contiene tu archivo index.html.</p>
                    <div class="code-block">
        📁 TuCarpeta/<br>
        └── index.html
                    </div>
                    <p>¡Suelta la carpeta en el área indicada y listo!</p>
                </div>
            </div>
            
            <div class="step">
                <div class="step-number">4</div>
                <div class="step-content">
                    <div class="step-title">Obtén tu URL</div>
                    <p>Netlify te asignará automáticamente una URL como: <strong>https://tu-app.netlify.app</strong></p>
                    <p>Puedes personalizar el nombre en la configuración del sitio.</p>
                    <div class="action-buttons">
                        <button class="btn btn-secondary" onclick="testDeploy()">
                            <i class="fas fa-play"></i> Probar despliegue
                        </button>
                    </div>
                </div>
            </div>
            
            <div class="demo-area">
                <div class="demo-title">Así se verá tu app Rappi</div>
                <div class="app-preview">
                    <div class="app-header">
                        <span>RappiClone</span>
                        <span>📍 Ciudad</span>
                    </div>
                    <div class="app-content">
                        <div class="restaurant-card">
                            <div class="restaurant-image">🍕</div>
                            <div class="restaurant-info">
                                <div class="restaurant-name">El Asador</div>
                                <div class="restaurant-details">⭐ 4.5 • 30-40 min • $100</div>
                            </div>
                        </div>
                        <div class="restaurant-card">
                            <div class="restaurant-image">🍣</div>
                            <div class="restaurant-info">
                                <div class="restaurant-name">Sushi Place</div>
                                <div class="restaurant-details">⭐ 4.8 • 25-35 min • $150</div>
                            </div>
                        </div>
                        <div class="restaurant-card">
                            <div class="restaurant-image">🍝</div>
                            <div class="restaurant-info">
                                <div class="restaurant-name">Pizza Italiana</div>
                                <div class="restaurant-details">⭐ 4.3 • 20-30 min • $120</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="success-message" id="success-message">
                <i class="fas fa-check-circle"></i> ¡Felicidades! Tu app Rappi está en línea. Comparte el enlace con tus amigos.
            </div>
            
            <div class="action-buttons" style="justify-content: center; margin-top: 30px;">
                <a href="https://app.netlify.com/signup" class="btn btn-primary" target="_blank">
                    <i class="fas fa-rocket"></i> Comenzar ahora en Netlify
                </a>
                <button class="btn btn-secondary" onclick="showVideoTutorial()">
                    <i class="fas fa-play-circle"></i> Ver tutorial en video
                </button>
            </div>
        </div>
        
        <footer>
            <p>Tu app Rappi estará online en menos de 5 minutos • Netlify es 100% gratis para proyectos personales</p>
        </footer>
    </div>

    <script>
        function downloadApp() {
            // Crear el contenido completo de la app Rappi
            const appContent = `<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RappiClone - Delivery App</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Todos los estilos de la app Rappi */
        :root {
            --primary-color: #00b8a9;
            --secondary-color: #ff8c00;
            --background-color: #f8f9fa;
            --card-color: #ffffff;
            --text-color: #333333;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--background-color);
            color: var(--text-color);
            padding-bottom: 70px;
            padding-top: 60px;
        }
        
        .header {
            background-color: var(--primary-color);
            color: white;
            padding: 15px;
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .search-bar {
            background-color: white;
            border-radius: 25px;
            padding: 10px 15px;
            margin: 10px;
            display: flex;
            align-items: center;
        }
        
        .search-bar input {
            border: none;
            outline: none;
            width: 100%;
            margin-left: 10px;
        }
        
        .categories {
            display: flex;
            overflow-x: auto;
            padding: 15px 10px;
            gap: 15px;
        }
        
        .category {
            display: flex;
            flex-direction: column;
            align-items: center;
            min-width: 70px;
        }
        
        .category-icon {
            background-color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .restaurants {
            padding: 10px;
        }
        
        .restaurant-card {
            background-color: var(--card-color);
            border-radius: 10px;
            overflow: hidden;
            margin-bottom: 15px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .restaurant-image {
            width: 100%;
            height: 150px;
            object-fit: cover;
        }
        
        .restaurant-info {
            padding: 10px;
        }
        
        .restaurant-name {
            font-weight: bold;
            margin-bottom: 5px;
        }
        
        .restaurant-details {
            display: flex;
            justify-content: space-between;
            color: #666;
            font-size: 14px;
        }
        
        .bottom-nav {
            position: fixed;
            bottom: 0;
            width: 100%;
            display: flex;
            justify-content: space-around;
            background-color: white;
            padding: 10px 0;
            box-shadow: 0 -2px 5px rgba(0,0,0,0.1);
        }
        
        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            font-size: 12px;
        }
        
        .nav-icon {
            font-size: 20px;
            margin-bottom: 3px;
        }
        
        .active {
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <div class="header">
        <div>
            <h1>RappiClone</h1>
        </div>
        <div>
            <span>📍 Ciudad</span>
        </div>
    </div>
    
    <div class="search-bar">
        <span>🔍</span>
        <input type="text" placeholder="Buscar restaurantes o comercios">
    </div>
    
    <div class="categories">
        <div class="category">
            <div class="category-icon">🍕</div>
            <span>Comida</span>
        </div>
        <div class="category">
            <div class="category-icon">🛒</div>
            <span>Super</span>
        </div>
        <div class="category">
            <div class="category-icon">🍺</div>
            <span>Bebidas</span>
        </div>
        <div class="category">
            <div class="category-icon">💊</div>
            <span>Farmacia</span>
        </div>
    </div>
    
    <div class="restaurants">
        <div class="restaurant-card">
            <img src="https://images.unsplash.com/photo-1513104890138-7c749659a591?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=800&q=80" class="restaurant-image" alt="Restaurante 1">
            <div class="restaurant-info">
                <div class="restaurant-name">El Asador</div>
                <div class="restaurant-details">
                    <span>⭐ 4.5 (250)</span>
                    <span>30-40 min</span>
                </div>
            </div>
        </div>
        
        <div class="restaurant-card">
            <img src="https://images.unsplash.com/photo-1572802419224-296b0aeee0d9?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=800&q=80" class="restaurant-image" alt="Restaurante 2">
            <div class="restaurant-info">
                <div class="restaurant-name">Sushi Place</div>
                <div class="restaurant-details">
                    <span>⭐ 4.8 (180)</span>
                    <span>25-35 min</span>
                </div>
            </div>
        </div>
        
        <div class="restaurant-card">
            <img src="https://images.unsplash.com/photo-1604068549290-dea0e4a305ca?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=800&q=80" class="restaurant-image" alt="Restaurante 3">
            <div class="restaurant-info">
                <div class="restaurant-name">Pizza Italiana</div>
                <div class="restaurant-details">
                    <span>⭐ 4.3 (320)</span>
                    <span>20-30 min</span>
                </div>
            </div>
        </div>
    </div>
    
    <div class="bottom-nav">
        <div class="nav-item active">
            <div class="nav-icon">🏠</div>
            <span>Inicio</span>
        </div>
        <div class="nav-item">
            <div class="nav-icon">🔍</div>
            <span>Buscar</span>
        </div>
        <div class="nav-item">
            <div class="nav-icon">📦</div>
            <span>Pedidos</span>
        </div>
        <div class="nav-item">
            <div class="nav-icon">👤</div>
            <span>Perfil</span>
        </div>
    </div>
</body>
</html>`;
            
            // Crear un blob y descargar
            const blob = new Blob([appContent], { type: 'text/html' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = 'rappi-clone.html';
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
            
            alert('¡App Rappi descargada! Ahora ve a Netlify para publicarla.');
        }
        
        function testDeploy() {
            document.getElementById('success-message').style.display = 'block';
            setTimeout(() => {
                document.getElementById('success-message').style.display = 'none';
            }, 5000);
        }
        
        function showVideoTutorial() {
            alert('Para un tutorial en video, busca "Cómo publicar en Netlify" en YouTube. Es muy sencillo: 1) Ve a netlify.com 2) Arrastra tu archivo HTML 3) ¡Listo!');
        }
    </script>
</body>
</html>

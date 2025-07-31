<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Business Model Canvas - Chicken Little</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #ff6b35 0%, #ff8c42 50%, #ffa726 100%);
            color: #333;
            padding: 15px;
            min-height: 100vh;
            animation: backgroundFloat 10s ease-in-out infinite;
        }
        
        @keyframes backgroundFloat {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }
        
        .header {
            text-align: center;
            margin-bottom: 25px;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            padding: 25px;
            border-radius: 25px;
            box-shadow: 0 20px 60px rgba(255, 107, 53, 0.3);
            border: 2px solid rgba(255, 255, 255, 0.8);
            position: relative;
            overflow: hidden;
        }
        
        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 107, 53, 0.1), transparent);
            animation: shimmer 3s ease-in-out infinite;
        }
        
        @keyframes shimmer {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }
        
        .logo-container {
            position: relative;
            width: 150px;
            height: 150px;
            margin: 0 auto 20px;
            animation: logoFloat 3s ease-in-out infinite;
        }
        
        @keyframes logoFloat {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-10px) rotate(2deg); }
        }
        
        .logo {
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #ff6b35, #ff8c42);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 15px 35px rgba(255, 107, 53, 0.4);
            position: relative;
            overflow: hidden;
        }
        
        .logo::before {
            content: '';
            position: absolute;
            top: 10%;
            left: 10%;
            right: 10%;
            bottom: 10%;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 50%;
            animation: pulse 2s ease-in-out infinite;
        }
        
        @keyframes pulse {
            0%, 100% { opacity: 0.2; transform: scale(1); }
            50% { opacity: 0.4; transform: scale(1.05); }
        }
        
        .chicken-mascot {
            font-size: 4em;
            animation: bounce 2s ease-in-out infinite;
            z-index: 2;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-5px); }
        }
        
        .brand-text {
            background: linear-gradient(45deg, #ff6b35, #ff8c42, #ffa726);
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            font-size: 3.5em;
            font-weight: 900;
            margin-bottom: 10px;
            text-shadow: 2px 2px 20px rgba(255, 107, 53, 0.3);
            letter-spacing: 2px;
        }
        
        .subtitle {
            color: #666;
            font-size: 1.4em;
            font-weight: 300;
            letter-spacing: 1px;
        }
        
        .canvas {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            grid-template-rows: auto auto auto;
            gap: 20px;
            max-width: 1500px;
            margin: 0 auto;
        }
        
        .canvas-block {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 25px;
            box-shadow: 0 15px 50px rgba(0, 0, 0, 0.1);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            border: 2px solid rgba(255, 255, 255, 0.8);
            position: relative;
            overflow: hidden;
        }
        
        .canvas-block::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 6px;
            background: linear-gradient(90deg, #ff6b35, #ff8c42, #ffa726);
            border-radius: 20px 20px 0 0;
        }
        
        .canvas-block:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 25px 80px rgba(255, 107, 53, 0.25);
            background: rgba(255, 255, 255, 1);
        }
        
        .canvas-block h3 {
            background: linear-gradient(45deg, #ff6b35, #ff8c42);
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            font-size: 1.5em;
            font-weight: 700;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 12px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .icon {
            width: 35px;
            height: 35px;
            border-radius: 50%;
            background: linear-gradient(135deg, #ff6b35, #ff8c42);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2em;
            box-shadow: 0 5px 15px rgba(255, 107, 53, 0.3);
            animation: iconPulse 2s ease-in-out infinite;
        }
        
        @keyframes iconPulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }
        
        .canvas-block ul {
            list-style: none;
            line-height: 1.8;
        }
        
        .canvas-block li {
            margin-bottom: 12px;
            padding: 10px 15px;
            background: linear-gradient(135deg, #fff8f6, #ffffff);
            border-radius: 10px;
            border-left: 4px solid #ff6b35;
            position: relative;
            color: #555;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .canvas-block li:hover {
            transform: translateX(5px);
            box-shadow: 0 5px 15px rgba(255, 107, 53, 0.1);
        }
        
        .canvas-block li::before {
            content: '🐔';
            position: absolute;
            left: -15px;
            top: 50%;
            transform: translateY(-50%);
            background: white;
            width: 25px;
            height: 25px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8em;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        
        .canvas-block p {
            line-height: 1.8;
            color: #555;
            margin-bottom: 15px;
            font-weight: 400;
        }
        
        /* Posicionamiento Grid */
        .socios { grid-column: 1; grid-row: 1; }
        .actividades { grid-column: 2; grid-row: 1; }
        .propuesta { grid-column: 3; grid-row: 1; }
        .relaciones { grid-column: 4; grid-row: 1; }
        .segmentos { grid-column: 5; grid-row: 1; }
        .recursos { grid-column: 2; grid-row: 2; }
        .canales { grid-column: 4; grid-row: 2; }
        .costos { grid-column: 1 / 3; grid-row: 3; }
        .ingresos { grid-column: 4 / 6; grid-row: 3; }
        
        /* Estilos especiales */
        .propuesta {
            background: linear-gradient(135deg, #fff5f2, #ffffff, #fff8f6);
            border: 3px solid #ff6b35;
            position: relative;
        }
        
        .propuesta::after {
            content: '⭐';
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 2em;
            animation: starTwinkle 2s ease-in-out infinite;
        }
        
        @keyframes starTwinkle {
            0%, 100% { opacity: 0.5; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.2); }
        }
        
        .costos, .ingresos {
            background: linear-gradient(135deg, #f8f9fa, #ffffff, #f1f3f4);
        }
        
        .price-item {
            background: linear-gradient(135deg, #fff5f2, #ffffff);
            padding: 15px 20px;
            margin: 10px 0;
            border-radius: 15px;
            border-left: 5px solid #ff6b35;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .price-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(255, 107, 53, 0.05), transparent);
            transform: translateX(-100%);
            transition: transform 0.6s ease;
        }
        
        .price-item:hover::before {
            transform: translateX(100%);
        }
        
        .price-item:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(255, 107, 53, 0.2);
        }
        
        .price-item strong {
            color: #ff6b35;
            font-weight: 700;
            font-size: 1.1em;
        }
        
        /* Responsive */
        @media (max-width: 1200px) {
            .canvas {
                grid-template-columns: repeat(3, 1fr);
                grid-template-rows: repeat(5, auto);
            }
            
            .socios { grid-column: 1; grid-row: 1; }
            .actividades { grid-column: 2; grid-row: 1; }
            .propuesta { grid-column: 3; grid-row: 1; }
            .recursos { grid-column: 1; grid-row: 2; }
            .relaciones { grid-column: 2; grid-row: 2; }
            .canales { grid-column: 3; grid-row: 2; }
            .segmentos { grid-column: 1 / 4; grid-row: 3; }
            .costos { grid-column: 1 / 4; grid-row: 4; }
            .ingresos { grid-column: 1 / 4; grid-row: 5; }
        }
        
        @media (max-width: 768px) {
            .canvas {
                grid-template-columns: 1fr;
                grid-template-rows: repeat(9, auto);
            }
            
            .canvas-block {
                grid-column: 1 !important;
                grid-row: auto !important;
            }
            
            .brand-text {
                font-size: 2.5em;
            }
            
            .logo-container {
                width: 120px;
                height: 120px;
            }
        }
        
        /* Partículas flotantes */
        .floating-particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .particle {
            position: absolute;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 0; }
            50% { transform: translateY(-100px) rotate(180deg); opacity: 1; }
        }
        
        .section-divider {
            text-align: center;
            margin: 30px 0;
            position: relative;
        }
        
        .section-divider::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 0;
            right: 0;
            height: 2px;
            background: linear-gradient(90deg, transparent, #ff6b35, transparent);
            transform: translateY(-50%);
        }
        
        .section-divider span {
            background: rgba(255, 255, 255, 0.9);
            padding: 10px 20px;
            border-radius: 25px;
            color: #ff6b35;
            font-weight: 600;
            position: relative;
            z-index: 1;
        }
    </style>
</head>
<body>
    <div class="floating-particles">
        <div class="particle" style="left: 10%; animation-delay: 0s; width: 4px; height: 4px;"></div>
        <div class="particle" style="left: 20%; animation-delay: 1s; width: 6px; height: 6px;"></div>
        <div class="particle" style="left: 30%; animation-delay: 2s; width: 3px; height: 3px;"></div>
        <div class="particle" style="left: 40%; animation-delay: 3s; width: 5px; height: 5px;"></div>
        <div class="particle" style="left: 50%; animation-delay: 4s; width: 4px; height: 4px;"></div>
        <div class="particle" style="left: 60%; animation-delay: 5s; width: 7px; height: 7px;"></div>
        <div class="particle" style="left: 70%; animation-delay: 1.5s; width: 3px; height: 3px;"></div>
        <div class="particle" style="left: 80%; animation-delay: 2.5s; width: 5px; height: 5px;"></div>
        <div class="particle" style="left: 90%; animation-delay: 3.5s; width: 4px; height: 4px;"></div>
    </div>

    <div class="header">
        <div class="logo-container">
            <div class="logo">
                <div class="chicken-mascot">🐔</div>
            </div>
        </div>
        <h1 class="brand-text">CHICKEN LITTLE</h1>
        <p class="subtitle">Business Model Canvas</p>
    </div>
    
    <div class="canvas">
        <div class="canvas-block socios">
            <h3><div class="icon">👥</div>Socios Clave</h3>
            <ul>
                <li>Isabella Romero Nieto</li>
                <li>Loren Isabella García Serna</li>
                <li>Nicolle Castro Romero</li>
                <li>Danna Valentina Nieto Garzón</li>
                <li>Felipe Barrero Romero</li>
            </ul>
        </div>
        
        <div class="canvas-block actividades">
            <h3><div class="icon">⚡</div>Actividades Clave</h3>
            <ul>
                <li>Equipo amable, atención y conocimiento de productos</li>
                <li>Establecer precios competitivos y ofertas especiales</li>
                <li>Espacio de trabajo limpio y ordenado</li>
            </ul>
        </div>
        
        <div class="canvas-block propuesta">
            <h3><div class="icon">💎</div>Propuesta de Valor</h3>
            <p>En <strong>Chicken Little</strong> ofrecemos una experiencia culinaria única a través de pollo asado, preparado con recetas secretas y condimentos originales, hechas por nosotros mismas.</p>
            <p>Nuestro producto principal es <strong>sabor, autenticidad, innovación y conciencia ambiental</strong>.</p>
        </div>
        
        <div class="canvas-block relaciones">
            <h3><div class="icon">🤝</div>Relación con Clientes</h3>
            <p>Aunque Chicken Little funcionará solo por un día, queremos que ese día el cliente se sienta bien recibido.</p>
            <p><strong>Atención presencial de calidad:</strong> durante la jornada, daremos un trato amable, ágil y atento.</p>
        </div>
        
        <div class="canvas-block segmentos">
            <h3><div class="icon">🎯</div>Segmentos de Clientes</h3>
            <p>Estos productos están diseñados para personas amantes del pollo desde niños hasta adultos que pueden consumir este tipo de productos.</p>
            <p>La mayoría de la gente le gusta y por esta razón jugamos con los precios para que cualquier persona pueda adquirir nuestros productos.</p>
        </div>
        
        <div class="canvas-block recursos">
            <h3><div class="icon">🔧</div>Recursos Clave</h3>
            <p>Los recursos clave de Chicken Little son los elementos fundamentales que necesitamos para preparar y ofrecer nuestros productos, así como para lograr una buena presentación y comunicación con los clientes.</p>
        </div>
        
        <div class="canvas-block canales">
            <h3><div class="icon">📢</div>Canales</h3>
            <p>Cuentas de la empresa promocionado los productos y la publicidad generada.</p>
        </div>
        
        <div class="canvas-block costos">
            <h3><div class="icon">💰</div>Estructura de Costos</h3>
            <div>
                <p><strong>🔒 Costos Fijos:</strong></p>
                <ul>
                    <li>Alquiler de espacios (ferias, locales)</li>
                    <li>Mantenimiento de equipos de cocina y maquinaria</li>
                </ul>
                
                <div class="section-divider">
                    <span>Variables</span>
                </div>
                
                <p><strong>📈 Costos Variables Principales:</strong></p>
                <ul>
                    <li><strong>Proteína Base (Pollo):</strong> Costo por kg/unidad según proveedor y temporada</li>
                    <li>Variación por tipo: convencional vs. orgánico/libre pastoreo</li>
                    <li>Diferencias por cortes: entero, pechugas, muslos, alas</li>
                    <li>Especias y condimentos esenciales</li>
                </ul>
            </div>
        </div>
        
        <div class="canvas-block ingresos">
            <h3><div class="icon">💵</div>Fuente de Ingresos</h3>
            <p>Los valores de los productos dependen de cuál de los servicios adquieren:</p>
            
            <div class="price-item">
                <strong>🍗 Un pollo completo + papá salada + arepa:</strong> $34,000
            </div>
            <div class="price-item">
                <strong>🍗 1/2 pollo + papá + arepa:</strong> $17,000
            </div>
            <div class="price-item">
                <strong>🍗 1/4 pollo + papá salada + arepa:</strong> $9,000
            </div>
            
            <div class="section-divider">
                <span>Presas Individuales</span>
            </div>
            
            <div class="price-item">
                <strong>🍗 Ala + papá + arepa:</strong> $4,000
            </div>
            <div class="price-item">
                <strong>🍗 Pierna + papá + arepa:</strong> $4,500
            </div>
            <div class="price-item">
                <strong>🍗 Cuadril + papá + arepa:</strong> $4,500
            </div>
            <div class="price-item">
                <strong>🍗 Pechuga + papá + arepa:</strong> $5,000
            </div>
            <div class="price-item">
                <strong>🥤 Bebidas (gaseosa/jugo pequeño):</strong> $1,500 - $5,500
            </div>
        </div>
    </div>
</body>
</html>

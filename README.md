Backend PetStore API Testing Project 🚀
📋 Descripción
Este proyecto implementa una suite completa de pruebas automatizadas para la API de PetStore, utilizando Postman/Newman como framework principal de testing. La automatización está integrada con GitHub Actions para CI/CD y la API de Postman, generando reportes detallados a través de Allure y HTMLExtra para un análisis profundo de los resultados.
🌟 Características Principales

Automatización completa de endpoints REST API
Integración con API de Postman para actualización automática de pruebas
Ejecución paralela de pruebas
Reportes detallados con Allure y HTMLExtra
Integración continua con GitHub Actions
Validación de esquemas JSON
Assertions avanzados
Variables de entorno configurables

🏗️ Estructura del Proyecto
CopyBackend_PetStore_API_Testing/
├── .github/
│   └── workflows/
│       └── postman-tests.yml    # Configuración de GitHub Actions
├── postman/
│   ├── collection.json          # Suite de pruebas Postman
│   └── environment.json         # Variables de ambiente
├── allure-report/              # Reportes Allure generados
├── allure-results/             # Datos de resultados Allure
├── newman/                     # Reportes HTMLExtra
├── .gitignore
├── package.json
└── README.md
📋 Prerrequisitos

Node.js (v20.x o superior)
npm (incluido con Node.js)
Git
Cuenta de GitHub
API Key de Postman configurada

🛠️ Instalación y Configuración
Instalación Local
bashCopy# Clonar el repositorio
git clone https://github.com/ElyerMaldonado/Backend_PetStore_API_Testing.git
cd Backend_PetStore_API_Testing

# Instalar dependencias globales
npm install -g newman@latest
npm install -g newman-reporter-htmlextra
npm install -g newman-reporter-allure

# Crear directorios necesarios
mkdir newman
mkdir allure-results
Configuración del Ambiente
bashCopy# Verificar instalación correcta
newman --version
npm list -g newman-reporter-htmlextra
npm list -g newman-reporter-allure
Configuración de Secretos

En GitHub, ir a Settings > Secrets > Actions
Crear nuevo secreto:

Nombre: POSTMAN_API_KEY
Valor: Tu API key de Postman



🚀 Ejecución de Pruebas
Ejecución Local
bashCopy# Ejecutar todas las pruebas con generación de reportes
newman run ./postman/collection.json -e ./postman/environment.json -r htmlextra,allure

# Ejecutar una colección específica
newman run ./postman/collection.json -e ./postman/environment.json --folder "Pet API Tests" -r htmlextra,allure

# Ejecutar con variables de ambiente personalizadas
newman run ./postman/collection.json -e ./postman/environment.json --env-var "baseUrl=https://petstore.swagger.io/v2" -r htmlextra,allure
📊 Reportes Generados
HTMLExtra Report (./newman/)

API Testing Coverage (Petstore)-[timestamp].html
Incluye:

Resumen de ejecución
Tiempo de respuesta
Pruebas fallidas/exitosas
Detalles de requests/responses



Allure Report
bashCopy# Generar reporte Allure
allure generate allure-results -o allure-report --clean

# Abrir reporte en navegador
allure open allure-report
🔄 Flujo de CI/CD
GitHub Actions
El workflow se activa automáticamente en:

Push a main
Pull Requests a main
Ejecución manual desde la interfaz de Actions
Actualizaciones en la colección de Postman (mediante API Key)

🌐 Visualización de Resultados

HTMLExtra Report: https://[username].github.io/Backend_PetStore_API_Testing/newman/
Allure Report: https://[username].github.io/Backend_PetStore_API_Testing/allure-report/

📝 Cobertura de Pruebas
Pet API

POST /pet - Crear nueva mascota
PUT /pet - Actualizar mascota existente
GET /pet/{petId} - Obtener mascota por ID
DELETE /pet/{petId} - Eliminar mascota

Store API

POST /store/order - Crear orden
GET /store/order/{orderId} - Obtener orden por ID
DELETE /store/order/{orderId} - Eliminar orden
GET /store/inventory - Obtener inventario

User API

POST /user - Crear usuario
GET /user/{username} - Obtener usuario por username
PUT /user/{username} - Actualizar usuario
DELETE /user/{username} - Eliminar usuario

🤝 Contribución

Fork el repositorio
Crea tu rama de feature
bashCopygit checkout -b feature/NuevaCaracteristica

Commit tus cambios
bashCopygit commit -m 'Agregada nueva característica XYZ'

Push a la rama
bashCopygit push origin feature/NuevaCaracteristica

Crea un Pull Request

👨‍💻 Autor
Elyer Gregorio Maldonado

GitHub: @ElyerMaldonado

📄 Licencia
Este proyecto está bajo la Licencia MIT - ver el archivo LICENSE.md para detalles.
🎯 Logros del Proyecto

✅ 100% de cobertura en endpoints principales
✅ Tiempo promedio de ejecución < 2 minutos
✅ Integración exitosa con CI/CD y API de Postman
✅ Reportes detallados y accesibles
✅ Documentación completa y mantenible

🔍 Notas Adicionales

Los reportes se actualizan automáticamente después de cada ejecución en GitHub Actions
Integración automática con Postman mediante API Key
Se mantiene un histórico de las últimas 10 ejecuciones
Las pruebas incluyen validaciones de esquema JSON para asegurar la integridad de los datos
Se implementan retry mechanisms para pruebas inestables

# Backend PetStore API Testing Project
Descripción
Este proyecto contiene pruebas automatizadas para la API de PetStore, implementadas usando Postman/Newman y configuradas para ejecutarse a través de GitHub Actions. Las pruebas cubren los principales endpoints de la API y generan reportes detallados usando Allure y HTMLExtra.
Estructura del Proyecto
CopyBackend_PetStore_API_Testing/
├── .github/
│   └── workflows/          # Configuraciones de GitHub Actions
├── postman/
│   ├── collections.json    # Colección de pruebas de Postman
│   └── environment.json    # Variables de ambiente
├── allure-report/         # Reportes generados por Allure
├── allure-results/        # Resultados de las pruebas
├── newman/                # Reportes HTMLExtra
└── package.json          # Dependencias del proyecto
Requisitos Previos

Node.js (versión 14 o superior)
npm (viene con Node.js)
Newman
Newman Reporter HTMLExtra
Newman Reporter Allure

Instalación Local

Clonar el repositorio:

bashCopygit clone [URL_DEL_REPOSITORIO]
cd Backend_PetStore_API_Testing

Instalar dependencias globales:

bashCopynpm install -g newman
npm install -g newman-reporter-htmlextra
npm install -g newman-reporter-allure
Ejecución de Pruebas
Localmente
Para ejecutar las pruebas en tu máquina local:
bashCopynewman run ./postman/collections.json -e ./postman/environment.json -r htmlextra,allure
GitHub Actions
Las pruebas se ejecutan automáticamente en GitHub Actions cuando:

Se hace push a la rama principal
Se crea un Pull Request

Reportes
El proyecto genera dos tipos de reportes:

HTMLExtra Report:

Disponible en la carpeta newman/
Proporciona una vista detallada de la ejecución de las pruebas

Allure Report:

Disponible en la carpeta allure-report/
Ofrece métricas y visualizaciones avanzadas de los resultados



Cobertura de Pruebas
Las pruebas cubren los siguientes endpoints de la API PetStore:

Gestión de Mascotas (Pet)
Gestión de Órdenes (Store)
Gestión de Usuarios (User)

CI/CD
El proyecto utiliza GitHub Actions para:

Ejecutar pruebas automáticamente
Generar reportes
Publicar resultados

Los resultados de las pruebas están disponibles en:
[URL_DE_GITHUB_PAGES]
Contribución

Fork el repositorio
Crea una rama para tu feature (git checkout -b feature/AmazingFeature)
Commit tus cambios (git commit -m 'Add some AmazingFeature')
Push a la rama (git push origin feature/AmazingFeature)
Abre un Pull Request

Autor
[Elyer Gregorio Maldonado]
Licencia
Este proyecto está bajo la Licencia MIT - ver el archivo LICENSE.md para más detalles.
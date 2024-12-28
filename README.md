Aquí tienes una versión mejorada del **README.md** para tu monorepo:

---

# Service Provider Monorepo

Este monorepo contiene los proyectos necesarios para implementar un **Service Provider (SP)** con soporte para autenticación **SAML2** y emisión de **JWT**, compuesto por un backend en **NestJS** y un frontend en **Next.js**.

---

## **Estructura del Proyecto**

```
/service-provider-monorepo
├── docker-compose.yml           # Orquestación de servicios con Docker Compose
├── service-provider/            # Backend (API en NestJS)
│   ├── Dockerfile               # Configuración Docker para el backend
│   ├── src/                     # Código fuente del backend
│   └── README.md                # Documentación específica del backend
├── service-provider-front/      # Frontend (Interfaz en Next.js)
│   ├── Dockerfile               # Configuración Docker para el frontend
│   ├── src/                     # Código fuente del frontend
│   └── README.md                # Documentación específica del frontend
```

---

## **Cómo Clonar y Configurar**

### Clonar el Repositorio con Submodules

Este repositorio utiliza **Git Submodules** para gestionar el backend y frontend como proyectos independientes. Para clonar y configurarlos correctamente:

```bash
git clone --recurse-submodules git@github.com:tu-usuario/service-provider-monorepo.git
```

Si ya clonaste el repositorio sin inicializar los submodules:

```bash
git submodule update --init --recursive
```

---

## **Cómo Ejecutar los Servicios**

El archivo `docker-compose.yml` te permite levantar tanto el backend como el frontend con un solo comando.

### Requisitos Previos

- **Docker** y **Docker Compose** instalados.

### Pasos

1. Ve a la raíz del monorepo.
2. Ejecuta el siguiente comando:
   ```bash
   docker-compose up --build
   ```

### Servicios Disponibles

- **Frontend**: [http://localhost:3000](http://localhost:3000)
- **Backend**: [http://localhost:3001](http://localhost:3001)

---

## **Scripts Útiles**

### Backend (`service-provider`)

Desde la carpeta `service-provider`, puedes usar estos comandos:

- **Instalar dependencias:**
  ```bash
  npm install
  ```
- **Levantar el servidor en desarrollo:**
  ```bash
  npm run start:dev
  ```

### Frontend (`service-provider-front`)

Desde la carpeta `service-provider-front`, puedes usar estos comandos:

- **Instalar dependencias:**
  ```bash
  npm install
  ```
- **Levantar el servidor en desarrollo:**
  ```bash
  npm run dev
  ```

---

## **Variables de Entorno**

Configura las siguientes variables de entorno en un archivo `.env` en las carpetas correspondientes.

### Backend (`service-provider`)

```env
JWT_SECRET=your_jwt_secret
SAML_ENTRYPOINT=https://idp.example.com/sso
SAML_ISSUER=http://localhost:3001
SAML_CERT=your_idp_certificate
```

### Frontend (`service-provider-front`)

```env
BACKEND_URL=http://localhost:3001
```

---

## **Contribuciones**

Si deseas contribuir:

1. Haz un fork del repositorio.
2. Crea una nueva rama para tus cambios:
   ```bash
   git checkout -b feature/nueva-funcionalidad
   ```
3. Realiza los cambios y agrega un commit descriptivo:
   ```bash
   git commit -m "Agrega soporte para nueva funcionalidad"
   ```
4. Sube tus cambios:
   ```bash
   git push origin feature/nueva-funcionalidad
   ```
5. Abre un **Pull Request**.

---

## **Licencia**

Este proyecto está licenciado bajo la [MIT License](./LICENSE).

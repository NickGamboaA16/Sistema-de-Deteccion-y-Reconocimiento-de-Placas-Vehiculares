# 🚗 Detector de Placas Vehiculares con YOLOv8
![Banner](https://github.com/user-attachments/assets/51f8e4ad-61ac-4fd9-acd7-ca5f33621aa7)

---

## 👥 Integrantes del Proyecto

- **Gamboa Agredo Nicolás** - Id: U00184047 -  Email: ngamboa847@unab.edu.co
- **Miranda Guerra Marcia Andrea** - Id:  -  Email: mmiranda666@unab.edu.co


---

## 📋 Descripción del Proyecto

Sistema completo de detección y reconocimiento automático de placas vehiculares que integra:

- **YOLOv8** para detección de objetos (placas en imágenes)
- **EasyOCR** para reconocimiento óptico de caracteres
- **FastAPI** como backend REST API
- **AWS EC2** para despliegue en la nube
- **React Native (Expo)** como aplicación móvil multiplataforma

Este sistema permite detectar y reconocer placas vehiculares a partir de imágenes o video, utilizando técnicas de visión artificial con YOLO. Los resultados son enviados a un backend que procesa la información y la muestra en una aplicación móvil.

---

## 🎯 Objetivos

### Objetivo General
Implementar un sistema de detección automática de placas vehiculares utilizando técnicas de visión por computadora y aprendizaje profundo, desplegado en infraestructura cloud.

### Objetivos Específicos
- Configurar y desplegar un servidor FastAPI en AWS EC2
- Integrar modelo YOLOv8 preentrenado para detección de placas
- Implementar reconocimiento de caracteres con EasyOCR
- Desarrollar aplicación móvil multiplataforma con React Native
- Documentar el proceso de despliegue completo

---

## 🛠️ Tecnologías Utilizadas

### Backend
- **Python 3.13**
- **FastAPI** - Framework web para APIs REST
- **Ultralytics YOLOv8** - Detección de objetos
- **EasyOCR** - Reconocimiento óptico de caracteres
- **OpenCV** - Procesamiento de imágenes
- **Uvicorn** - Servidor ASGI

### Frontend
- **React Native** - Framework móvil
- **Expo** - Plataforma de desarrollo
- **TypeScript** - Lenguaje de programación
- **Axios** - Cliente HTTP

### Infraestructura
- **AWS EC2** - Servidor virtual (T2.Large)
- **AWS Learner Lab** - Ambiente educativo
- **Ubuntu 22.04** - Sistema operativo

---

## 📁 Estructura del Repositorio
```
Detector-Placas-YOLO/
├── backend/              # Código del servidor FastAPI
├── mobile-app/           # Aplicación móvil React Native
└── README.md             # Este archivo
```

---

## ⚙️💻 Guía de Despliegue

### 1️⃣ Backend (AWS EC2)
<img width="1900" height="912" alt="aws" src="https://github.com/user-attachments/assets/0404a6e6-299c-4281-beb8-14b64701b6ad" />

---
<img width="1583" height="307" alt="aws2" src="https://github.com/user-attachments/assets/36bb3700-2e77-48ef-aacd-29ca621b5674" />

---
<img width="1912" height="882" alt="aws3" src="https://github.com/user-attachments/assets/5887702b-5797-49fa-9213-404626d8d399" />


---
#### Configuración de la Instancia

**Especificaciones:**
- Tipo: `t2.large`
- Sistema Operativo: Ubuntu 22.04 LTS
- Almacenamiento: 32 GiB
- Puertos abiertos: 22 (SSH), 8080 (API)

<img width="1528" height="747" alt="aws4" src="https://github.com/user-attachments/assets/e4f384c4-dc87-4ed6-b15f-17a5dfc0e1de" />

---
#### Instalación de Dependencias
```bash
# Actualizar sistema
sudo apt update
sudo apt install -y python3-pip python3-venv libgl1 libglib2.0-0

# Crear entorno virtual
mkdir proyecto && cd proyecto
python3 -m venv venv
source venv/bin/activate

# Instalar librerías
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu
pip install ultralytics fastapi uvicorn easyocr opencv-python-headless pillow numpy python-multipart
```
<img width="561" height="165" alt="image" src="https://github.com/user-attachments/assets/308c3d31-2e9b-4eff-a873-30b90ae1369e" />

---

#### Ejecución del Servidor
```bash
# Activar entorno virtual
cd proyecto
source venv/bin/activate

# Ejecutar servidor
python3 app.py
```
---

<img width="1896" height="633" alt="resp" src="https://github.com/user-attachments/assets/e90c3d91-0084-4331-b679-14d251d5665e" />

---
Respuesta del servidor a peticiones
---

<img width="813" height="753" alt="REspuesta2" src="https://github.com/user-attachments/assets/a925b537-d846-4049-904a-bf457805b547" />

---
El servidor estará disponible en: `http://52.201.115.189:8080`

---

### 2️⃣ Aplicación Móvil (React Native + Expo)

#### Requisitos Previos
- Node.js 18+
- npm 9+
- Expo Go (app móvil)

#### Instalación
```bash
# Clonar repositorio
git clone [URL_DEL_REPO]
cd Detector-Placas-YOLO/mobile-app

# Instalar dependencias
npm install --legacy-peer-deps

# Configurar IP del servidor
# Editar App.tsx, línea 6:
const API_URL = 'http://52.201.115.189:8080';
```

#### Ejecución
```bash
# Modo desarrollo
npx expo start

# Con túnel (para redes diferentes)
npx expo start --tunnel
Escanear el código QR con:
- **Android:** App Expo Go
- **iOS:** Cámara del iPhone
```
<img width="1920" height="1020" alt="Lanzado" src="https://github.com/user-attachments/assets/e08cadf0-5f03-40b7-b192-9b1cbd1bb910" />

---
Dispositivo IOS conectado
---
<img width="1920" height="1020" alt="lanzado2" src="https://github.com/user-attachments/assets/0457edb6-47ce-4bf8-920b-609ef00f6cd6" />

---
Dispositivo Android conectado
---

<img width="1920" height="1020" alt="lanzado3" src="https://github.com/user-attachments/assets/e020b975-bf76-4c80-8b85-4d3724ccd6e8" />



## 📸 Evidencias de Funcionamiento

### Backend
---
Consumo y verificación de la API del backend mediante Postman.
![carroprueba](https://github.com/user-attachments/assets/9454611d-426b-4100-8fe1-4b2600058e97)

<img width="1783" height="866" alt="image" src="https://github.com/user-attachments/assets/08d50c24-fdd4-412e-adbc-a1a6718e2388" />

### FrontEnd
---
Ejecución en Expo Go

<img width="720" height="1452" alt="ExpoGo" src="https://github.com/user-attachments/assets/fb21dd8c-fbf9-4943-99ee-992fe7e40867" />

![WhatsApp Image 2025-12-04 at 5 13 54 PM (8)](https://github.com/user-attachments/assets/2b24602e-e19c-489f-a37c-437aac542ae5)

![WhatsApp Image 2025-12-04 at 5 13 54 PM (7)](https://github.com/user-attachments/assets/523db652-d9d1-4ef4-b542-88eef9d05f82)

![WhatsApp Image 2025-12-04 at 5 13 54 PM (4)](https://github.com/user-attachments/assets/e45310be-c2dd-4fc4-bae1-08206dfa01ef)
![WhatsApp Image 2025-12-04 at 5 13 54 PM (3)](https://github.com/user-attachments/assets/c57a0b52-5ef8-48a5-970c-96cdad02ecde)
![WhatsApp Image 2025-12-04 at 5 13 54 PM (2)](https://github.com/user-attachments/assets/5cf05ebb-d2fa-43fd-8b1e-d421e56687b8)
![WhatsApp Image 2025-12-04 at 5 13 54 PM (1)](https://github.com/user-attachments/assets/2746d57d-eeaa-439d-89bd-58a2c0a148a9)
![WhatsApp Image 2025-12-04 at 5 13 54 PM (5)](https://github.com/user-attachments/assets/f34ffcee-dc1f-437f-a526-1ab711da87d2)
![WhatsApp Image 2025-12-04 at 5 13 55 PM (1)](https://github.com/user-attachments/assets/d82ec0d6-f7bb-408a-9326-67f5eef8fa88)


https://github.com/user-attachments/assets/e924b47f-8d41-42e2-9290-bd3a12fc8934


---
Ejecución Desde La App en Android
---
![WhatsApp Image 2025-12-04 at 4 37 19 PM (2)](https://github.com/user-attachments/assets/a00947e8-5e57-4374-98a0-c55643f6b37d)

![WhatsApp Image 2025-12-04 at 4 37 19 PM](https://github.com/user-attachments/assets/dfe47554-b024-4eb7-a2c3-66a254b5e6a2)

![WhatsApp Image 2025-12-04 at 4 37 19 PM (5)](https://github.com/user-attachments/assets/7d4903db-ea7a-4c07-88e0-c241bbc65f36)
![WhatsApp Image 2025-12-04 at 4 37 19 PM (4)](https://github.com/user-attachments/assets/d71b2f18-bb25-47b8-8d02-9a5c3041aaed)



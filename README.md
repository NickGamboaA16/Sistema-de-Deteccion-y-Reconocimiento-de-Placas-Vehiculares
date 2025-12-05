# 🚗 Detector de Placas Vehiculares con YOLOv8
![Banner](https://github.com/user-attachments/assets/51f8e4ad-61ac-4fd9-acd7-ca5f33621aa7)

---

## 👥 Integrantes del Proyecto

- **Gamboa Agredo Nicolás** -  Email: ngamboa847@unab.edu.co
- **Miranda Guerra Marcia Andrea** -  Email: mmiranda666@unab.edu.co


---

## 📋 Descripción del Proyecto

Sistema completo de detección y reconocimiento automático de placas vehiculares que integra:

- **YOLOv8** para detección de objetos (placas en imágenes)
- **EasyOCR** para reconocimiento óptico de caracteres
- **FastAPI** como backend REST API
- **AWS EC2** para despliegue en la nube
- **React Native (Expo)** como aplicación móvil multiplataforma

El sistema permite capturar o seleccionar una imagen de un vehículo y obtener automáticamente el texto de su placa vehicular mediante inteligencia artificial.

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
├── evidencias/           # Capturas de pantalla del proyecto
│   ├── backend/          # Evidencias del backend
│   └── frontend/         # Evidencias de la app móvil
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
<img width="1528" height="747" alt="aws4" src="https://github.com/user-attachments/assets/e4f384c4-dc87-4ed6-b15f-17a5dfc0e1de" />

---
#### Configuración de la Instancia

**Especificaciones:**
- Tipo: `t2.large`
- Sistema Operativo: Ubuntu 22.04 LTS
- Almacenamiento: 32 GiB
- Puertos abiertos: 22 (SSH), 8080 (API)

<img width="1920" height="1020" alt="back" src="https://github.com/user-attachments/assets/e1a67c48-851d-478f-a3fb-43ffb534f2af" />

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
<img width="1397" height="962" alt="despl" src="https://github.com/user-attachments/assets/c310e4b8-c0e2-420d-9adb-c20a521efe3b" />

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

<img width="813" height="753" alt="REspuesta2" src="https://github.com/user-attachments/assets/a925b537-d846-4049-904a-bf457805b547" />

---
El servidor estará disponible en: `http://IP_PUBLICA:8080`

---

### 2️⃣ Aplicación Móvil (React Native + Expo)

<img width="1920" height="1020" alt="Lanzado" src="https://github.com/user-attachments/assets/e08cadf0-5f03-40b7-b192-9b1cbd1bb910" />

---
<img width="1920" height="1020" alt="lanzado2" src="https://github.com/user-attachments/assets/0457edb6-47ce-4bf8-920b-609ef00f6cd6" />

---

<img width="1920" height="1020" alt="lanzado3" src="https://github.com/user-attachments/assets/e020b975-bf76-4c80-8b85-4d3724ccd6e8" />

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
const API_URL = 'http://TU_IP_EC2:8080';
```

#### Ejecución
```bash
# Modo desarrollo
npx expo start

# Con túnel (para redes diferentes)
npx expo start --tunnel
```

Escanear el código QR con:
- **Android:** App Expo Go
- **iOS:** Cámara del iPhone

---

## 📸 Evidencias de Funcionamiento

### Backend






# 🛡️ Offensive Security & Infra Development Lab

![CRT-ID](https://shields.io)
![Status](https://shields.io)

Este repositorio documenta el arsenal técnico y los laboratorios de infraestructura desarrollados bajo los estándares de la certificación **CRT-ID (CyberWarFare Labs)**.

---

## 🛠️ I. Red Team Infrastructure & Exploitation

### ⚡ Escalada de Privilegios y Sudo Bypass
Uso de `sudo -S` para automatizar la elevación de privilegios en post-explotación:
```bash
echo 'password' | sudo -S whoami
```

### 🛰️ Network Sniffing (Raw Sockets)
Intercepción de tráfico en Capa 2 usando Python y Scapy para análisis de protocolos.

---

## 🐍 II. Herramientas de Explotación (Python)

### 🔑 FTP Brute Forcer
Script para auditoría de credenciales en servicios FTP.
```python
import ftplib

def bruteforce(target, user, password):
    ftp = ftplib.FTP(target)
    try:
        ftp.login(user, password)
        print(f'[+] Éxito: {user}:{password}')
    except:
        print(f'[-] Falló: {user}:{password}')
```

### 🌍 OSINT & IP Geolocalización
Módulo de reconocimiento pasivo mediante la API de IPInfo.
```python
import ipinfo
import requests

def get_location(token):
    ip = requests.get("https://ipify.org").text
    handler = ipinfo.getHandler(token)
    details = handler.getDetails(ip)
    for key, value in details.all.items():
        print(f"{key}: {value}")
```
## 🌐 IV. API Penetration Testing (OWASP API Top 10)
Enfoque en la seguridad de servicios web y microservicios.

### 🛠️ Herramientas Utilizadas
*   **Postman/Insomnia:** Para pruebas de endpoints y automatización de peticiones.
*   **Burp Suite:** Intercepción y manipulación de tráfico API.
*   **ffuf/Gobuster:** Fuzzing de rutas y parámetros ocultos.

### 🛡️ Pruebas de Autorización (BOLA/IDOR)
Ejemplo de testeo de vulnerabilidad de Broken Object Level Authorization:
```bash
# Intento de acceso a un recurso de otro usuario cambiando el ID en la URL
GET /api/v1/user/1005/profile  # Original
GET /api/v1/user/1006/profile  # Intento de IDOR
```

---

## 🎓 Certificaciones Actualizadas
*   **CRT-ID**: Certified Red Team Infra Dev - *CyberWarFare Labs*
*   **API Penetration Testing**: *APISec University* (2025)

---

## ☣️ III. Análisis de Malware (Droppers)
Estudio de vectores de infección inicial mediante archivos `.bat` generados dinámicamente en C para evasión básica.

---

## 🎓 Certificaciones
*   **CRT-ID**: Certified Red Team Infra Dev - *CyberWarFare Labs* (2025)

---
> [!NOTE]  
> Este laboratorio es estrictamente para fines de investigación y desarrollo de capacidades ofensivas éticas.

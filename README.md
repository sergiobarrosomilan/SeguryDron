# SeguryDron S.A. - Infraestructura Tecnológica para Vigilancia Aérea

## 📝 Descripción del Proyecto
Este proyecto consiste en el diseño, desarrollo e implementación de la infraestructura informática integral, segura y escalable para **SeguryDron S.A.**, una compañía de seguridad privada especializada en la vigilancia aérea mediante drones profesionales. 

Desarrollado como **Proyecto Intermodular de 2º de Grado Medio en Sistemas Microinformáticos y Redes (SMR)**.

---

## 🛠️ Tecnologías y Herramientas Utilizadas

* **Sistemas Operativos:** Windows Server 2022 (Controlador de Dominio), Windows 11 Pro (Estaciones de control).
* **Servicios de Red:** Active Directory DS, DNS, DHCP, SMB, RTSP (Puerto 554 para streaming de drones).
* **Almacenamiento:** NAS Synology DiskStation DS925+ (Configuración RAID).
* **Infraestructura y Redes:** Ubiquiti UniFi Dream Machine Pro (Router/Firewall), Switch gestionable L2 TP-Link JetStream (TL-SL3428).
* **Plataforma Web:** Interfaz de usuario y panel de control desarrollados en WordPress (Entorno IIS + MySQL + PHP) bajo protocolo seguro HTTPS.
* **Ciberseguridad:** Bitdefender GravityZone (Antivirus Corporativo), Firewall de Windows avanzado, políticas de contraseñas y auditoría de logs.
* **Simulación y Diseño:** Cisco Packet Tracer y Oracle VM VirtualBox.

---

## 📐 Arquitectura de la Solución
El sistema está diseñado en una arquitectura cliente-servidor de 3 capas:
1. **Presentación (Frontend):** Interfaz web corporativa en WordPress para el registro de vuelos y subida de vídeos (Formatos MP4/MOV, máx 500MB).
2. **Lógica de Negocio (Backend):** Servidor Windows Server que valida credenciales en Active Directory y procesa la auditoría.
3. **Capa de Datos:** Almacenamiento persistente en el NAS Synology mapeado automáticamente mediante directivas de grupo (GPO) como la **Unidad Z:**.

---

## 🚀 Pruebas y Verificación del Sistema

### 1. Entorno Virtualizado (VirtualBox)
Se realizaron pruebas exitosas interconectando el cliente Windows 11 al dominio `segurydron.local`. 
* Validación del canal seguro del dominio mediante PowerShell.
* Verificación de la persistencia de la **Unidad Z:** de manera automática mediante GPO para nuevos usuarios creados (`Tecnico2`).

### 2. Simulación de Red (Cisco Packet Tracer)
Se diseñó la topología completa interconectando el Centro de Operaciones (LAN) con las unidades de campo (WLAN mediante seguridad WPA2-AES).
* Pruebas de conectividad ICMP (Ping) entre el Dron-DJI y el Servidor Central con 0% de pérdida de paquetes.
* Resolución de nombres exitosa mediante `nslookup segurydron.local`.

---

## 📁 Estructura del Repositorio
* `/docs`: Contiene la documentación oficial en formato PDF.
* `/src`: Contiene scripts de automatización en PowerShell utilizados durante el despliegue.
* `/assets`: Diagramas de casos de uso, diagrama de clases, secuencia y capturas de las simulaciones.

---
**Autor:** Sergio Barroso Milán  
*Estudiante de Sistemas Microinformáticos y Redes*

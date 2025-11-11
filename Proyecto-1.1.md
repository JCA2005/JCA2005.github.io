summary: Bastionado de la BIOS/UEFI de Lenovo Legion 7-16ACHg6
id: Proyecto-1.1
categories: ciberseguridad, lenovo, bios, uefi, hardening
environments: web
status: Published
feedback link: https://github.com/JCA2005
authors: Javier Calvillo Acebedo

# CodeLab: Bastionar la BIOS/UEFI (Lenovo Legion 7-16ACHg6 - simulador)

## Objetivos

- Incrementar la seguridad del proceso de arranque (BIOS/UEFI).
- Configurar contraseñas adecuadas (administrador y usuario / Power-On).
- Evitar arranques desde dispositivos externos.
- Establecer un orden de arranque seguro.
- Activar Secure Boot y TPM (si procede).
- Documentar la configuración y explicar mitigaciones contra Clear CMOS.

## Requisitos previos

1. Cuenta en GitHub (para publicar la guía en GitHub Pages).
2. Acceso al simulador de Lenovo: https://download.lenovo.com/bsco/index.html#/ (navegador con JavaScript habilitado).
3. Un navegador moderno (Chrome/Edge/Firefox).
4. Opcional: copiar/pegar estas instrucciones en un editor Markdown y probarlas en el simulador.

## Nota importante sobre el simulador

El simulador de Lenovo es una herramienta web interactiva. Si al abrir la página ves el mensaje "Please enable JavaScript to use the website", habilita JavaScript y recarga la página. Busca el modelo **Legion 7-16ACHg6 (82N6)** o un modelo equivalente si no aparece exactamente.

## Paso a paso

### 1) Abrir el simulador y seleccionar modelo

1. Abre: `https://download.lenovo.com/bsco/index.html#/`
2. Busca el modelo **Legion 7-16ACHg6** o el código **82N6**.
3. Selecciona el equipo en la lista.

### 2) Entrar al menú principal de la UEFI/BIOS

1. Haz clic en la pantalla del BIOS/UEFI.
2. Localiza las pestañas: **Main**, **Security**, **Boot**, **Exit**.

### 3) Establecer contraseña de administrador

1. En **Security** o **Authentication**, busca **Set Supervisor Password**.
2. Introduce una contraseña robusta (mínimo 12 caracteres, mezcla de mayúsculas, minúsculas, números y símbolos).

### 4) Establecer contraseña de arranque (Power-On / HDD / User Password)

1. En **Security** o **Boot**, busca **Set User Password**, **Power-On Password** o **HDD Password**.
2. Introduce la contraseña según tu política.

### 5) Deshabilitar arranque desde dispositivos externos

1. En **Boot** o **Startup**, busca **Boot from USB**, **External Device Boot**, **Network Boot (PXE)**.
2. Cambia a **Disabled**.

### 6) Establecer orden de arranque seguro

1. En **Boot Priority / Boot Order**, selecciona el disco interno como **First Boot Device**.
2. Mueve unidades extraíbles y Network Boot al final.

### 7) Habilitar Secure Boot

1. En **Security** o **Boot**, busca **Secure Boot** y habilítalo.
2. Modo: **Standard** o **Windows UEFI mode**.

### 8) Habilitar TPM / Security Chip

1. Busca **Security Chip**, **TPM**, **PTT** (Intel) o **fTPM** (AMD) y actívalo.

### 9) Desactivar Legacy/CSM

1. En **Boot**, busca **CSM Support / Legacy Boot** y establece **Disabled**.

## Checklist

- [ ] Contraseña Power-On
- [ ] Contraseña Supervisor
- [ ] Evitar arranques externos
- [ ] Orden de arranque seguro
- [ ] Secure Boot, TPM, CSM
- [ ] Mitigaciones frente a Clear CMOS y copias de seguridad

# T03: Servidor de fitxers

## Introducció
Quan el volum de negoci creix, també ho fa el volum de dades i sovint aquí comencen els problemes. La informació es compartimenta, de manera que manca una visió global de la situació.

**FoodLogistic** no ha estat una excepció: cada departament guardava la documentació de forma local. És per això que un dels requisits de l’encàrrec que n’heu rebut és solucionar aquest problema.

L'objectiu és implementar una infraestructura de fitxers **segura, organitzada i amb control d'espai**, utilitzant:
- Permisos **NTFS/SMB**
- **Quotes**
- Filtratge de fitxers (**FSRM**)

Haureu de demostrar el domini de les tres vies d'administració:
- Explorador de fitxers  
- Server Manager  
- PowerShell  

---

## 🧩 Descripció de l'activitat

L'activitat es divideix en fites que simulen el procés de consultoria i implementació real.

---

## 1️⃣ Preparació i Seguretat de Grups (AD)

Abans de crear el servidor de fitxers, cal preparar l’**Active Directory**.

- Domini: `foodlogistic.test`
- Crear una estructura d’**OUs** coherent (justificada)

### Grups de seguretat:
- **Administracio** → Gestió de factures i albarans  
- **Transport** → Xofers i caps de flota  
- **Direccio** → Gerència  

---

## 2️⃣ Implementació de Recursos Compartits (Tres mètodes)

Heu de crear les següents estructures de carpetes al servidor:

---

### 📁 A. Carpeta Public (Explorador d'arxius)

- Compartida per a tothom  
- **Permisos SMB:** Lectura  
- **Permisos NTFS:** Modificació  
- Verificar permisos efectius  

---

### 📁 B. Carpeta Operacions (Server Manager - FSSM)

- Instal·lar rol **File and Storage Services**  
- Crear recurs compartit  
- Activar **Access-Based Enumeration (ABE)**  
- **Restricció:** només grup **Transport**  

---

### 📁 C. Carpeta Confidencial (PowerShell bàsic)

- Crear carpeta: `Direccio$` (oculta)  
- **Restricció:** només grup **Direccio**  
- Cmdlet: `New-SmbShare`  

- Configurar **GPO**:
  - Assignar unitat **Z:**  
  - Només per usuaris de Direcció  

---

### 📁 D. Carpeta Confidencial (PowerShell avançat)

- Crear carpeta: `Direccio`  
- **Restricció:** només grup **Direccio**  
- Cmdlet: `New-SmbShare`  
- Activar **Access-Based Enumeration** via PowerShell  

- Configurar **GPO**:
  - Assignar unitat **Z:**  
  - Només per usuaris de Direcció  

> ⚠️ Heu de triar entre el mètode **C o D** (el **D** té més valoració)

---

## 3️⃣ Control d'Emmagatzematge (FSRM i Quotes NTFS)

El client es queixa que els usuaris guarden arxius personals i omplen el disc.

---

### 💾 Quotes NTFS (per volum)

- Activar quotes a la unitat de dades  
- Límit per defecte: **500 MB per usuari**  

---

### 📊 FSRM (per carpeta)

#### 📁 Carpeta Public
- Quota de **200 MB (Hard Quota)**  
- Avís al **90%** amb missatge:
  > "Compte! FoodLogístic t'informa que estàs a punt d'esgotar l'espai compartit."

#### 📁 Carpeta Operacions
- Filtrat de fitxers:
  - Bloquejar `.exe`, `.msi`  
  - Bloquejar arxius d’àudio i vídeo  

---

## 4️⃣ Verificació i Auditoria

Des d’un client Windows 10/11:

- Verificar accés segons grups  
- Comprovar visibilitat de carpetes  

### 🧪 Proves:
- Intentar copiar un `.exe` a **Operacions**  
- Canviar extensió `.exe` → `.txt`  
  - El servidor ho permet?  

---

## 📦 Què cal lliurar

Informe tècnic en **format Markdown** amb:

### 📋 Resum de configuració
Taula amb:
- Nom de carpeta  
- Camí UNC  
- Grups amb accés  
- Mètode utilitzat  

---

### 📸 Evidències
- Captures de pantalla  
- Explicacions de:
  - Permisos  
  - Recursos compartits  
  - Quotes  
  - Filtres  

---

### ✅ Proves de funcionament
- Verificació des de clients  
- Control d’accés  
- Funcionament de quotes  
- Restriccions de fitxers  
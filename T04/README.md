# T04: Servidor d’impressió

## Introducció
En el món de la logística, la impressió continua tenint un paper molt important: albarans, fulls de transport, etc. necessiten ser impresos. El vostre client no és una excepció.

L'empresa té un magatzem on el volum d'impressió d'albarans és crític. Si una impressora falla o es col·lapsa, els camions no poden sortir, cosa que trenca la cadena de fred.

L'objectiu d'aquesta activitat és configurar un **Servidor d'Impressió a Windows Server** que gestioni aquest volum mitjançant el **Printer Pooling** (cua d’impressió compartida) per balancejar la càrrega entre dos dispositius.

---

## 🧩 Descripció de l'activitat

El servidor haurà de tenir implementats:
- **Active Directory**
- **Servei de servidor d’impressió**

Això permetrà:
- Gestió centralitzada d’usuaris i equips  
- Accés als recursos d’impressió des dels clients  

El client (Windows 10/11), integrat al domini, haurà de:
- Autenticar-se amb credencials de xarxa  
- Accedir a les impressores compartides  

📌 **Important:**  
Cal documentar tot el procés com un **informe tècnic professional**, amb:
- Explicacions clares  
- Estructura ordenada  
- Justificació de decisions  

---

## ⚙️ Fases de l’activitat

---

## 1️⃣ Preparació de l'entorn i simulació de maquinari

- Verificar o preparar l’entorn necessari  
- Instal·lar **dues instàncies de PDF24** al servidor  
  - Seguir la guia de suport  

### 🖨️ Nom de les impressores:
- `IMP_MAGATZEM_A`  
- `IMP_MAGATZEM_B`  

---

## 2️⃣ Instal·lació del rol i configuració del Pool

### 🔧 Instal·lació
- Instal·lar el rol **Print and Document Services**  
- Accedir a la consola **Print Management**  

### 🔄 Configuració del Printer Pooling

1. Obrir propietats de `IMP_MAGATZEM_A`  
2. Pestanya **Ports**  
3. Activar:
   - ✅ *Enable printer pooling*  
4. Seleccionar el port de `IMP_MAGATZEM_B`  

📌 **Resultat:**
- Les dues impressores funcionen com una sola  
- El sistema reparteix la càrrega automàticament  

⚠️ **Nota tècnica:**
A `IMP_MAGATZEM_A` han de quedar seleccionats **dos ports virtuals**  

---

## 3️⃣ Desplegament automatitzat amb GPO

L’empresa no vol instal·lacions manuals.

### 🧾 Configuració:

- Crear GPO:
  - `GPO_Impressores_Magatzem`

- Des de **Print Management**:
  - Opció: *Deploy with Group Policy*  
  - Vincular a:
    - Domini o OU específica  

### 🧪 Verificació:
- Iniciar sessió en client Windows 11  
- La impressora apareix automàticament  

⚠️ **Nota tècnica:**
- Reiniciar sessió o executar:
```bash
gpupdate /force
```
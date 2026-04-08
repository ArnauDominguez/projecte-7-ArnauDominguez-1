# T11: Preparem una intranet per a més endavant - Aplicacions web

## Introducció
En aquest projecte es planteja la creació d’una intranet corporativa basada en WordPress per a un client que necessita millorar la comunicació interna i la gestió de la informació.

L’objectiu és implementar una plataforma web interna que permeti als treballadors:

- Compartir documents
- Treballar amb documents online
- Gestionar el correu electrònic
- Organitzar calendaris i tasques
- Accedir a tota la informació des d’un únic portal web

La solució escollida és utilitzar **WordPress** com a base, ampliant les seves funcionalitats mitjançant plugins específics.

---

## 🎯 Objectius del projecte

- Instal·lar WordPress en un entorn local o servidor
- Configurar una intranet funcional
- Afegir funcionalitats mitjançant plugins
- Garantir l’accés restringit només a usuaris interns
- Documentar tot el procés tècnic

---

## ⚙️ Fase 1: Instal·lació de WordPress

### Passos realitzats:
1. Instal·lació de servidor local (Laragon/XAMPP)
2. Creació de base de dades MySQL
3. Descàrrega de WordPress
4. Configuració inicial (usuari administrador, idioma, etc.)

### Comentaris tècnics:
- WordPress requereix PHP i MySQL
- És recomanable utilitzar HTTPS fins i tot en entorns locals

---

## 🔐 Fase 2: Configuració d’accés (Intranet)

### Objectiu:
Restringir l’accés només a usuaris de l’empresa.

### Solució:
- Instal·lació de plugin: *WP Private Content* o similar
- Configuració de:
  - Accés amb login obligatori
  - Rols d’usuari (administrador, editor, empleat)

### Resultat:
Només els usuaris registrats poden accedir al contingut de la intranet.

---

## 📂 Fase 3: Compartició de documents

### Plugins utilitzats:
- WP Document Revisions
- o alternatives com FileBird

### Funcionalitats:
- Pujar arxius
- Control de versions
- Compartició interna

---

## 📝 Fase 4: Treball amb documents online

### Opcions implementades:
- Integració amb Google Docs (enllaços)
- Plugins de visualització de documents

### Resultat:
Els usuaris poden visualitzar i editar documents al núvol.

---

## 📧 Fase 5: Gestió del correu electrònic

### Solució:
- Integració amb serveis externs (Gmail / Outlook)
- Accés via enllaç dins la intranet

### Comentari:
WordPress no gestiona correu directament, però pot centralitzar accessos.

---

## 📅 Fase 6: Calendaris i tasques

### Plugins utilitzats:
- The Events Calendar
- WP Project Manager

### Funcionalitats:
- Creació d’esdeveniments
- Assignació de tasques
- Seguiment de projectes

---

## 🌐 Fase 7: Portal centralitzat

### Estructura creada:
- Inici (dashboard)
- Documents
- Correu
- Calendari
- Tasques

### Objectiu:
Facilitar l’accés a tota la informació des d’un únic lloc.

---

## ⚠️ Problemes trobats i solucions

| Problema                         | Solució                              |
|--------------------------------|--------------------------------------|
| Error connexió base de dades    | Revisar credencials MySQL           |
| Plugins incompatibles           | Buscar alternatives actualitzades    |
| Accés públic no desitjat        | Configurar plugin de restricció      |

---

## 📸 Evidències

*(Afegir captures de pantalla de:)*  
- Instal·lació WordPress  
- Plugins configurats  
- Pantalla de login  
- Intranet en funcionament  

---

## 📄 Conclusions

La implementació d’una intranet amb WordPress és una solució:

- Flexible i escalable
- Econòmica per a PIMES
- Fàcil de gestionar

Permet centralitzar serveis i millorar la productivitat dels treballadors.

---

## 📦 Lliurament

Cal entregar un **informe tècnic en PDF** que inclogui:

- Explicació de cada fase
- Captures de pantalla
- Comentaris tècnics
- Problemes i solucions

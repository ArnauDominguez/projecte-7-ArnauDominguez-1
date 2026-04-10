## **Fase 1: Coneixent el terreny i la competència**

### **1\. Recerca de mercat: Empreses al Maresme**

Hem seleccionat tres perfils d'empreses de serveis IT a la zona de Mataró per entendre el panorama:

| Empresa | Mida | Especialització |
| :---- | :---- | :---- |
| **Punt de Gir** (Mataró) | PIME | Consultoria, manteniment IT, seguretat i solucions Cloud. |
| **Inforber** (Presència a Mataró/Maresme) | PIME | ERP (Software de gestió), sistemes i manteniment integral. |
| **Micrograme** (Mataró) | Microempresa | Manteniment de proximitat, hardware i reparacions. |

###  **2\. L'Organigrama (Codi PlantUML)**

Prenent com a referència una PIME de serveis informàtics mitjana de Mataró, hem estructurat la jerarquia següent. Aquest model permet separar clarament la part tècnica de la comercial.
```bash
@startuml
skinparam Monochrome true
skinparam shadowing false

title Organigrama d'una PIME de Serveis IT (Mataró)

package "Direcció General" {
    [CEO / Gerència] as CEO
}

package "Departament Tècnic" {
    [Director Tècnic (CTO)] as CTO
    [Àrea de Sistemes i Cloud] as Sistemes
    [Suport / Helpdesk] as Suport
    [Àrea de Desenvolupament / ERP] as Software
}

package "Departament Comercial i Màrqueting" {
    [Director Comercial] as Vendes
    [Consultor Pre-venda] as Prevenda
}

package "Administració" {
    [Administració i RH] as Admin
}

CEO --> CTO
CEO --> Vendes
CEO --> Admin

CTO --> Sistemes
CTO --> Suport
CTO --> Software

Vendes --> Prevenda

@enduml
```
### **3\. Radiografia de departaments**

Per a una empresa que vulgui donar servei a FoodLogístic, aquests són els pilars essencials:

* Sistemes i Infraestructura: S'encarrega del "ferro" i el núvol. Servidors, seguretat (firewalls) i xarxes Wi-Fi per a la nau logística.  
* Suport / Helpdesk: El primer punt de contacte. Resolen incidències del dia a dia (impressores, correus, bloquejos d'usuari). Crucial per a la continuïtat del negoci.  
* Comercial i Pre-venda: No només venen, sinó que analitzen les necessitats del client per oferir solucions a mida abans de signar el contracte.  
* Administració: Gestió de facturació, compres de llicències i contractes de manteniment.

## **Fase 2: Estratègia**

### **1\. Definició de la Proposta de Valor**

Per guanyar el contracte de FoodLogístic davant de la competència, la nostra estratègia es basarà en la Especialització Logística i Proximitat Extrema:

* Proximitat "Kilòmetre Zero": En estar també a Mataró, garantim un temps de resposta presencial inferior a 1 hora en cas de fallada crítica a la nau.  
* Especialització en Mobilitat: Coneixement profund en xarxes Wi-Fi industrials i dispositius de radiofreqüència (PDA), vitals per a un magatzem logístic.  
* Monitoratge 24/7 de Sistemes Crítics: Les cambres frigorífiques i la logística no descansen; els seus sistemes tampoc haurien de fer-ho.

### **2\. Recursos Necessaris**

Com que som una empresa que "tot just arrenca", hem d'avaluar si podem cobrir a FoodLogístic:

* Perfils actuals (Equip Fundador): Segurament perfils polivalents (Sistemes \+ Comercial).  
* Necessitat de contractació:  
  * Tècnic de Suport N1: Si FoodLogístic té molts treballadors de magatzem, necessitarem una persona dedicada exclusivament a les incidències diàries per no bloquejar els fundadors.  
  * Expert en Ciberseguretat (Extern/Freelance): Per a la renovació a fons, potser caldrà subcontractar una auditoria inicial per assegurar que la nova infraestructura és resilient.

Conclusió: Per tancar el client amb garanties, hauríem de preveure la contractació d'almenys un tècnic de suport junior per mantenir el nivell de servei (SLA) promès en la proposta.


@startgantt
title Planificació Projecte FoodLogístic S.A.
language ca

' Definició d'estils per a claredat visual
<style>
ganttDiagram {
    task {
        BackGroundColor AliceBlue
        LineColor RoyalBlue
    }
    .critic {
        BackGroundColor LightCoral
        LineColor Red
    }
}
</style>

' --- FASE 1: INICI I ANÀLISI ---
[T01: Estudi competència i sector] lasts 3 days
[T01] is colored in #LightCoral 
' El posem com a crític perquè d'ell penja tota la branca web i legal

' --- FASE 2: DESENVOLUPAMENT EN PARAL·LEL ---

' Branca Crítica (Web i Legal)
[T02: Web corporativa (proposta)] lasts 8 days
[T02] starts at [T01]'s end
[T02] is colored in #LightCoral

[T06: Adaptació web normativa legal] lasts 6 days
[T06] starts at [T02]'s end
[T06] is colored in #LightCoral

[T08: Tria web definitiva (consens)] lasts 3 days
[T08] starts at [T06]'s end
[T08] is colored in #LightCoral

' Branca Sistemes i Formació (Tenen marge/slack)
[T03: Servidor de fitxers (AD+NTFS)] lasts 8 days
[T03] starts at [T01]'s end

[T04: Servidor d'impressió (GPO)] lasts 4 days
[T04] starts at [T03]'s end

[T05: Vídeo formatiu LOPD] lasts 8 days
[T05] starts at [T01]'s end

[T07: Migració al cloud (SaaS)] lasts 4 days
[T07] starts at [T01]'s end

' --- FASE 3: TANCAMENT I DOCUMENTACIÓ ---
[T09: Diagrama de Gantt + planificació] lasts 7 days
[T09] starts at [T08]'s end

[T10: Pressupost del projecte] lasts 4 days
' Depèn de SaaS (T07) i Sistemes (T03/T04)
[T10] starts at [T04]'s end
[T10] starts at [T07]'s end
[T10] starts at [T08]'s end

' Marcador de fites (Milestones)
[Entrega Final Projecte] happens at [T10]'s end

@endgantt

![img](imatges/img1.png)
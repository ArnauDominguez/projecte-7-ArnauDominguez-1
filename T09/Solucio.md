@startgantt
title Cronograma FoodLogístic S.A. - 30 Dies
language ca
printscale daily

' --- FASE 1: INICI ---
[T01: Estudi competència i sector] lasts 6 days
[T01] is colored in #FF9999

' --- FASE 2: DESENVOLUPAMENT ---
[T02: Web corporativa (desenvolupament)] lasts 12 days
[T02] starts at [T01]'s end
[T02] is colored in #FF9999

[T06: Adaptació normativa legal] lasts 6 days
[T06] starts at [T02]'s end
[T06] is colored in #FF9999

' Tasques en paral·lel
[T03: Servidor de fitxers (AD + NTFS)] lasts 14 days
[T03] starts at [T01]'s end

[T04: Servidor d'impressió (GPO)] lasts 5 days
[T04] starts at [T03]'s end

[T05: Vídeo formatiu LOPD] lasts 15 days
[T05] starts at [T01]'s end

[T07: Migració al cloud (SaaS)] lasts 7 days
[T07] starts at [T01]'s end

' --- FASE 3: TANCAMENT ---
[T08: Tria web definitiva i fusió] lasts 4 days
[T08] starts at [T06]'s end
[T08] is colored in #FF9999

[T09: Diagrama de Gantt i Memòria] lasts 3 days
[T09] starts at [T08]'s end
[T09] is colored in #FF9999

[T10: Pressupost final del projecte] lasts 3 days
[T10] starts at [T09]'s start
[T10] starts at [T04]'s end
[T10] starts at [T07]'s end
[T10] is colored in #FF9999

[FINALITZACIÓ] happens at [T10]'s end
@endgantt


![img](imatges/img1.png)
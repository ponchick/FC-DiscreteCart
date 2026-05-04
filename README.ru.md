# FC-DiscreteCart

Плата картриджа для Famicom / Dendy на элементах дискретной логики.

Поддерживаются следующие типы плат (boards):  
NROM, CNROM, GNROM, BNROM, AMROM, ANROM, AOROM, UNROM, UOROM.

## Настройка перемычек

Все перемычки, кроме JP1, настраиваются согласно таблице ниже.  
JP1 (VRAM_A10) задаёт зеркалирование видеопамяти – см. пояснение после таблицы.

| ROM type | U1 type | U2 type | U3 74161 | U4 7432 | U5 7402 | JP1 VRAM_A10 | JP2 PRG_OE | JP3 CHR_PIN26 | JP4 CHR_PIN27 | JP5 161_Q2 | JP6 161_Q3 | JP7 PRG_A14 | JP8 PRG_A15 | JP9 PRG_A15 | JP10 PRG_A16 | JP11 PRG_A16 | JP12 PRG_A17 |
| :--- | :--- | :--- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| NROM | ROM 16kB/32kB | ROM 8kB | ✗ | ✗ | ✗ | V/H* | ![соединить 2–3](assets/2-2.png) | ![соединить 2–3](assets/2-2.png) | ![соединить 2–4](assets/3-3.png) | ![не соединять](assets/2-0.png) | ![не соединять](assets/3-0.png) | ![соединить 1–2](assets/2-1.png) | ![не соединять](assets/2-0.png) | ![соединить 2–3](assets/2-2.png) | ![не соединять](assets/2-0.png) | ![соединить 2–3](assets/2-2.png) | ![соединить 2–4](assets/3-3.png) |
| CNROM | ROM 16kB/32kB | ROM 32kB | ✓ | ✗ | ✗ | V/H* | ![соединить 2–3](assets/2-2.png) | ![соединить 1–2](assets/2-1.png) | ![соединить 1–2](assets/3-1.png) | ![соединить 1–2](assets/2-1.png) | ![соединить 2–4](assets/3-3.png) | ![соединить 1–2](assets/2-1.png) | ![не соединять](assets/2-0.png) | ![соединить 2–3](assets/2-2.png) | ![не соединять](assets/2-0.png) | ![соединить 2–3](assets/2-2.png) | ![соединить 2–4](assets/3-3.png) |
| GNROM | ROM 128kB | ROM 32kB | ✓ | ✗ | ✗ | V/H* | ![соединить 2–3](assets/2-2.png) | ![соединить 1–2](assets/2-1.png) | ![соединить 1–2](assets/3-1.png) | ![соединить 1–2](assets/2-1.png) | ![соединить 2–4](assets/3-3.png) | ![соединить 1–2](assets/2-1.png) | ![соединить 1–2](assets/2-1.png) | ![не соединять](assets/2-0.png) | ![не соединять](assets/2-0.png) | ![соединить 1–2](assets/2-1.png) | ![соединить 2–4](assets/3-3.png) |
| AMROM | ROM 128kB | RAM 8kB | ✓ | ✗ | ✗ | ![соединить 2–4](assets/3-3.png) | ![соединить 2–3](assets/2-2.png) | ![соединить 2–3](assets/2-2.png) | ![соединить 2–3](assets/3-2.png) | ![соединить 2–3](assets/2-2.png) | ![соединить 2–3](assets/3-2.png) | ![соединить 1–2](assets/2-1.png) | ![соединить 2–3](assets/2-2.png) | ![не соединять](assets/2-0.png) | ![соединить 2–3](assets/2-2.png) | ![не соединять](assets/2-0.png) | ![соединить 2–3](assets/3-2.png) |
| ANROM / AOROM | ROM 128kB/256kB | RAM 8kB | ✓ | ✗ | ✓ | ![соединить 2–4](assets/3-3.png) | ![соединить 1–2](assets/2-1.png) | ![соединить 2–3](assets/2-2.png) | ![соединить 2–3](assets/3-2.png) | ![соединить 2–3](assets/2-2.png) | ![соединить 2–3](assets/3-2.png) | ![соединить 1–2](assets/2-1.png) | ![соединить 2–3](assets/2-2.png) | ![не соединять](assets/2-0.png) | ![соединить 2–3](assets/2-2.png) | ![не соединять](assets/2-0.png) | ![соединить 2–3](assets/3-2.png) |
| BNROM | ROM 128kB | RAM 8kB | ✓ | ✗ | ✗ | V/H* | ![соединить 2–3](assets/2-2.png) | ![соединить 2–3](assets/2-2.png) | ![соединить 2–3](assets/3-2.png) | ![соединить 2–3](assets/2-2.png) | ![соединить 2–3](assets/3-2.png) | ![соединить 1–2](assets/2-1.png) | ![соединить 2–3](assets/2-2.png) | ![не соединять](assets/2-0.png) | ![соединить 2–3](assets/2-2.png) | ![не соединять](assets/2-0.png) | ![соединить 2–3](assets/3-2.png) |
| UxROM | ROM 256kB | RAM 8kB | ✓ | ✓ | ✗ | V/H* | ![соединить 2–3](assets/2-2.png) | ![соединить 2–3](assets/2-2.png) | ![соединить 2–3](assets/3-2.png) | ![соединить 2–3](assets/2-2.png) | ![соединить 1–2](assets/3-1.png) | ![соединить 2–3](assets/2-2.png) | ![не соединять](assets/2-0.png) | ![соединить 1–2](assets/2-1.png) | ![соединить 1–2](assets/2-1.png) | ![не соединять](assets/2-0.png) | ![соединить 1–2](assets/3-1.png) |

\* Настройка JP1 (VRAM_A10) зависит от требуемого зеркалирования видеопамяти:

| Зеркалирование | Положение JP1 |
| --- | --- |
| Vertical | ![соединить 1–2](assets/3-1.png) |
| Horizontal | ![соединить 2–3](assets/3-2.png) |

## Лицензия

Проект распространяется под лицензией **CERN Open Hardware Licence Version 2 – Permissive** (`CERN-OHL-P-2.0`).  
Подробности в файле `LICENSE`.  

SPDX-License-Identifier: `CERN-OHL-P-2.0`

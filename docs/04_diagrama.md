## Diagrama de estados

```mermaid
---
config:
  layout: elk
  look: neo
---
flowchart TB
    n1(("S0")) --> n2@{ label: "C*T'" } & n3["R"]
    n2 --> n4(("S1"))
    n3 --> n1
    n4 --> n6@{ label: "C'+T+R" } & n7["Alarma"]
    n6 --> n1
    n7 --> n5(("S2"))
    n5 --> n8["R"] & n9@{ label: "R'" }
    n8 --> n1
    n9 --> n5

    n2@{ shape: text}
    n3@{ shape: text}
    n6@{ shape: text}
    n7@{ shape: text}
    n8@{ shape: text}
    n9@{ shape: text}
    style n1 font-size:24px
    style n4 font-size:24px
    style n5 font-size:24px
```


# 03. Máquina de estados

## 1. Descripción

La máquina de estados controla el funcionamiento de una bomba de agua mediante un ESP32. El sistema opera en tres estados: reposo, bombeo y alarma enclavada.

## 2. Variables de entrada

| Variable | Tipo | Descripción |
|---|---|---|
| `C` | Digital | `1`: hay agua suficiente en la cisterna. `0`: agua insuficiente. |
| `T` | Digital | `1`: el tinaco está lleno. `0`: el tinaco no está lleno. |
| `R` | Digital | `1`: se solicita restablecimiento manual. `0`: sin solicitud. |
| `Alarma` | Interna | `1`: se superó el tiempo máximo de bombeo. |

## 3. Definición de estados

| Estado | Nombre | Comportamiento |
|---|---|---|
| `S0` | Reposo | Bomba apagada y alarma no enclavada. |
| `S1` | Bombeo | Bomba encendida y temporizador de seguridad activo. |
| `S2` | Alarma enclavada | Bomba apagada; requiere restablecimiento manual. |

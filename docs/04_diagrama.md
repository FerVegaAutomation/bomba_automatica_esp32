###Diagrama de estados

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


C = 1: hay agua suficiente en la cisterna.
T = 1: el tinaco está lleno.
R = 1: se solicita restablecimiento manual.
Alarma = 1: se superó el tiempo máximo permitido de bombeo.
B = 1: comando de encendido de la bomba.
S0: bomba apagada y sin alarma enclavada.
S1: bomba encendida y temporizador activo.
S2: bomba apagada y alarma enclavada.

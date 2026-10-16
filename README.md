# Sistema de bombeo automático con ESP32

## Descripción
Proyecto de automatización doméstica para controlar el bombeo de agua desde una cisterna hacia un tinaco, con modos manual y automático, protección mediante temporizador y registro de datos para analizar el consumo de agua.

## Objetivo
Diseñar e implementar un sistema que automatice el llenado del tinaco, evite condiciones de operación insegura y permita registrar y analizar el comportamiento del consumo de agua.

## Funcionalidades previstas
- Control automático del nivel del tinaco.
- Modos manual y automático.
- Protección por falta de agua en la cisterna.
- Temporizador de seguridad con alarma enclavada.
- Medición del volumen bombeado y del consumo doméstico.
- Almacenamiento local y sincronización con la nube.
- Consulta de históricos y estadísticas de consumo.

## Controlador
ESP32.

## Estados de la máquina
- **S0:** reposo, bomba apagada.
- **S1:** bombeo, bomba y temporizador habilitados.
- **S2:** alarma enclavada, bomba apagada hasta el restablecimiento manual.

## Estado actual
Fase 1: diseño e ingeniería de requerimientos.

## Tecnologías previstas
- ESP32 y programación en C/C++.
- Sensores de nivel y caudal.
- Control digital y temporización.
- Almacenamiento local y servicios en la nube.

## Documentación
La documentación técnica, los diagramas, la lista de entradas y salidas y los resultados de las pruebas se incorporarán progresivamente.

## Seguridad
El sistema deberá incluir protecciones eléctricas adecuadas para la bomba. Las protecciones críticas no dependerán de la conectividad a Internet.

## Autor
Proyecto personal de ingeniería electrónica y automatización industrial.

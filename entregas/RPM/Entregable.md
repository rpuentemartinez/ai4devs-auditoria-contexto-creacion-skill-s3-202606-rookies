# Entregable · Sesión 3 — Copilotos IA

- **Nombre / usuario:**
- **Fecha de entrega:**22/06/2026 (Entregado por error en otro Repo en esa fecha)
- **Repo auditado en la Parte A** (solo tipo/contexto, NO el código): _p. ej. "monorepo TypeScript de trabajo, ~8 meses"_
Repo de un proyecto propio en C#/Blazor

---

## 1. Hallazgos de la auditoría (Parte A)

> 3-5 cosas que el agente **no pudo inferir** del código y que tendrías que decirle explícitamente.
> Redáctalas para que otra persona las entienda sin contexto adicional. **Sin código propietario ni secretos.**

1. No fue capaz de identificar el workflow del proceso de autentificación de la aplicación
2. No ha sido capaz de interpretar cual es la finalidad de la aplicación
3. No ha interpretado las clases de datos por lo que no hay una definición de para que sirve cada una de ellas, ni siquiera las ha enumerado
4. No ha podido inferir cuales son las reglas de codificación
5. No ha podido determinar los criterios de aceptación

---

## 2. SKILL.md de la skill creada (Parte B)

> Pega aquí el contenido completo de tu `.claude/skills/<nombre-skill>/SKILL.md`
> (o enlaza al archivo en tu repositorio sandbox).

```markdown
---
name: commit-convention
description: Genera un mensaje de commit siguiendo la especificación Conventional Commits a partir de los cambios. Úsalo cuando el usuario diga "genera un commit", "mensaje de commit", "escribe el commit", "/commit-convention".
---

# Generador de mensajes de commit (Conventional Commits)

Genera un mensaje de commit conforme a Conventional Commits a partir del diff del repositorio. El idioma será en español salvo que se indque otro idioma especificamente.

## Flujo

1. **Obten los cambios**

2. **Analiza el diff** para determinar el **tipo-commit**.

3. **Redacta el mensaje** con el formato de abajo. NO hagas el commit salvo que el usuario lo pida explícitamente.


## Formato

```
<tipo-commit (obligatorio)>(<scope (opcional)>): <descripción (obligatorio)>

<cuerpo>

```

### tipo-commit (obligatorio):
- `feat` — nueva funcionalidad
- `fix` — corrección de bug
- `docs` — solo documentación
- `style` — formato, sin cambio de lógica (espacios, comas, etc.)
- `refactor` — cambio que ni corrige bug ni añade feature
- `perf` — mejora de rendimiento
- `test` — añade o corrige tests
- `build` — sistema de build o dependencias (csproj, NuGet, npm)
- `ci` — configuración CI/CD
- `chore` — tareas de mantenimiento sin tocar src ni test
- `revert` — revierte un commit previo

### Reglas de la descripción (subject)
- El mensaje debe ser lo mas resumido posible pero suficientemente claro.
- Mensaje en **español** salvo que el usuario indque otro
- Si el diff mezcla cosas no relacionadas, sugiere dividir en varios commits y propón un mensaje por cada uno. 

## Ejemplos

```
feat(asignaciones): añade endpoint para cerrar asignación por vehículo
```

```
fix(auth): valida expiración del token antes de refrescar

El gate de MainLayout refrescaba el token incluso cuando seguía
vigente, generando llamadas innecesarias a la API de seguridad.
```
```

---

## 3. Diario de decisiones

*Skill creada:* 
commit-convention
Genera un mensaje de commit siguiendo la especificación Conventional Commits a partir de los cambios existentes

*Decisiones de diseño tomadas:*
- Decisión 1: Como la nombre y como la puedo invocar
- Decisión 2: Idioma a usar
- Decisión 3: Flujo a seguir
- Decisión 4: Incluyo ejemplos?
- Decisión 5: Incluyo reglas

*Qué me resultó fácil:*
- Dar la descripción

*Qué me resultó ambiguo o difícil de decidir:*
- Como comienzo o doy estructura al documento (que debo incluir y como se lo indico)

*Tiempo real invertido:*
  Tiempo total:60m 
  Lectura previa: 20m
  Diseño y escritura: 40m

*Qué probarías si tuvieras más tiempo:*
- Controlar los posibles casos de error (Ej: No es un repositorio git)

*¿Usaste IA para crear la skill?* (qué partes generaste con IA y qué partes decidiste tú)
- Le pedi un esqueleto base del Skill que queria hacer y sobre el mismo modifique, agrege y elimine.

### Resultado de la prueba (Paso 8)

¿Se activó cuando esperabas?
SI

¿El resultado fue el que querías?
Si, me sorprendio que fue capaz de encontrar que se trataban de modificaciones muy diferentes y me propuso 2 commits como le indicaba en las reglas

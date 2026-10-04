# 🐾 WISERVET — Desafío Congreso

Juego del Colchagua Business Veterinary 2026, convertido en **app instalable que funciona 100 % sin internet** (PWA).
Es el mismo juego aprobado: no se tocaron preguntas, textos, ruleta, colores, timer ni resultados.

## Qué se agregó

| Agregado | Para qué |
|---|---|
| Ícono **WISERVET** en la pantalla de inicio | Se abre a pantalla completa, sin barra de Chrome, en horizontal |
| Funciona en **modo avión** ✈️ | La app queda guardada en la tablet después de abrirla una vez con internet |
| **🟢 X PARTICIPACIONES GUARDADAS** | Contador arriba de la tabla de registros |
| **📊 DESCARGAR EXCEL** | Guarda `wiservet_registros_AAAA-MM-DD_HHMM.xlsx` en **Archivos → Descargas** |
| **📦 RESPALDAR REGISTROS** | Guarda `wiservet_backup_AAAA-MM-DD_HHMM.json` en **Archivos → Descargas** |
| **📥 IMPORTAR RESPALDO** | Recupera registros desde un respaldo (no borra ni duplica nada) |
| Doble guardado | Cada registro se guarda en `localStorage` **y** en IndexedDB; si uno se pierde, se recupera del otro |

También se restauró el logo transparente (resultado, reunión y esquina inferior), que venía dañado en el prototipo y no se veía.

## Publicar (una sola vez)

La app necesita estar en una dirección `https://` para poder instalarse. Lo más simple es GitHub Pages (gratis):

1. En GitHub: **Settings → Pages**.
2. *Source*: **Deploy from a branch**. *Branch*: la rama con estos archivos (por ejemplo `main`), carpeta **/ (root)**. **Save**.
3. En 1–2 minutos queda en `https://fbarrosp97.github.io/ruleta/`.

> GitHub Pages en repos privados requiere un plan pago de GitHub. Si el repo es privado, se puede hacer público:
> el código no tiene datos de participantes (los registros nunca salen de la tablet).

## Instalar en la Samsung Galaxy Tab S10 Lite

1. Con internet, abrir **Chrome** y entrar a `https://fbarrosp97.github.io/ruleta/`.
2. Menú **⋮ → Agregar a pantalla de inicio → Instalar**.
3. Abrir la app desde el ícono **WISERVET** una vez con internet. Listo: desde ahí funciona en modo avión.

## ⚠️ Importante durante el evento

- **Respaldar seguido.** Cada 1–2 horas: *VER REGISTROS → 📦 RESPALDAR REGISTROS*. Al final del día, también **📊 DESCARGAR EXCEL**.
- **No borrar los datos de Chrome** (*Ajustes → Privacidad → Borrar datos de navegación*), **no borrar los datos de la app** y **no desinstalarla**:
  eso borra los registros. Cerrar la app, apagar o reiniciar la tablet **no** los borra.
- Los registros quedan **solo en esa tablet**. No se suben a ningún servidor. El link de WhatsApp solo se genera y se guarda;
  no se envía nada solo.
- Si en algún momento cambia la dirección web de la app, los registros no se traspasan: usar **📥 IMPORTAR RESPALDO**.

## Actualizar la app

Editar `index.html`, cambiar `CACHE = 'wiservet-v1'` a `'wiservet-v2'` en `sw.js` y publicar.
La tablet toma la versión nueva la segunda vez que se abre con internet. **Los registros se mantienen.**

## Checklist de pruebas antes del congreso

| # | Prueba | OK |
|---|---|---|
| 1 | Instalar desde Chrome (ícono WISERVET en el inicio) | ☐ |
| 2 | Activar modo avión y abrir la app | ☐ |
| 3 | Crear participante | ☐ |
| 4–6 | Jugar y que salgan Clínica, Financiero y Clientes (girar varias veces) | ☐ |
| 7–8 | Responder Sí/No con notas distintas (P1 Sí "Lo sabe aproximadamente", P2 No "Lo revisa con contador", P3 Sí "Tiene el dato", P4 No "No sabe", P5 Sí "Lo ve mensualmente") | ☐ |
| 9 | VER REGISTROS: P1 Sí · P2 No · P3 Sí · P4 No · P5 Sí y notas correctas | ☐ |
| 10–11 | Cerrar la app por completo (quitarla de recientes) y abrir: el registro sigue | ☐ |
| 12 | Reiniciar la tablet: el registro sigue | ☐ |
| 13–14 | En modo avión, crear otro participante | ☐ |
| 15–16 | 📊 DESCARGAR EXCEL y abrirlo desde **Archivos → Descargas**: todas las columnas y datos | ☐ |
| 17 | 📦 RESPALDAR REGISTROS: aparece el `.json` en Descargas | ☐ |
| 18 | 📥 IMPORTAR RESPALDO en otro navegador/tablet: aparecen los registros | ☐ |

## Archivos

- `index.html` — el juego (todo incluido: logos, Excel, lógica)
- `manifest.webmanifest` — nombre, ícono, pantalla completa y orientación horizontal
- `sw.js` — guarda la app en la tablet para que funcione sin internet
- `icons/` — íconos de la app

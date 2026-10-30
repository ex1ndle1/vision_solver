# VisionSolverAI — сайт загрузки

Простой статический сайт для скачивания `VisionSolverAI-Windows-x64.exe`.

## Что внутри

- `site/index.html` — страница (лендинг)
- `site/style.css` — стили
- `render.yaml` — blueprint для Render (static site, publish path `- site`)

## Настройка ссылки на скачивание

Ссылка ведёт на GitHub Releases. Замени в `site/index.html` плейсхолдер:

```
https://github.com/ВАШ_ЛОГИН/ВАШ_РЕПОЗИТОРИЙ/releases/latest/download/VisionSolverAI-Windows-x64.exe
```

на свой репозиторий (он стоит в двух местах: кнопка в шапке-герое и секция «Скачать»).

### Как залить exe в Releases

```bash
# создать тег и релиз
gh release create v1.0.0 VisionSolverAI-Windows-x64.exe \
  --title "VisionSolverAI v1.0.0" \
  --notes "First Windows x64 build"
```

После этого ссылка `releases/latest/download/...` всегда будет отдавать файл из последнего релиза.

## Деплой на Render

Вариант 1 — через Blueprint: в Render → **New → Blueprint** → выбрать этот репозиторий, конфиг возьмётся из `render.yaml`.

Вариант 2 — вручную: Render → **New → Static Site** → подключить репозиторий:

- Build Command: (пусто)
- Publish Directory: `site`

## Локальный просмотр

```bash
cd site && python -m http.server 8000
```

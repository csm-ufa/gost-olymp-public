## Лендинг Олимпиады стандартов

### стек
- vite
- svelte-kit
- tailwindcss

### предисловие
Установите NodeJS с официального сайта <a href=https://nodejs.org/en/download target="_blabk">nodejs.org</a> на вашу ОС.

Либо загрузите образ используя docker:
```bash
docker pull node
```

### сборка
1. перейдите в директорию проекта;
2. установите зависимости NodeJS;
```bash
npm ci
```
3. собирите проект;
```bash
npm run build
```
4. скопируйте файлы из директории ./build (в корне проекта), в директорию вашего веб-сервера.

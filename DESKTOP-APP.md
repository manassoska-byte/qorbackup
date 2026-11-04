# QorBackup Desktop Application

QorBackup енді Tauri 2 негізіндегі desktop application foundation-ға ие. Қазіргі интерфейс React/Tailwind арқылы жасалған, Tauri оны Windows, macOS және Linux терезесіне орайды.

## Қазіргі native мүмкіндіктер

- Tauri 2 Rust shell.
- QorBackup атауы, терезе өлшемі және desktop bundle metadataсы.
- Native folder picker: Tauri ішінде жүйелік папка таңдау терезесі ашылады.
- Браузер Preview үшін mock picker fallback.
- Tauri CLI командалары: `pnpm tauri:dev` және `pnpm tauri:build`.

## Жергілікті іске қосу

Алдымен Node.js, pnpm, Rust stable және Tauri жүйелік тәуелділіктерін орнату керек. Windows-та Visual Studio Build Tools және WebView2, macOS-та Xcode Command Line Tools, Linux-та `webkit2gtk-4.1` және `librsvg2-dev` керек.

```bash
pnpm install
pnpm tauri:dev
```

Орнатылатын desktop bundle жасау үшін:

```bash
pnpm tauri:build
```

Build нәтижесі `src-tauri/target/release/bundle/` ішіне түседі. Windows-та `.msi` немесе `.exe`, macOS-та `.dmg`, Linux-та `.deb`/`.AppImage` түрлері жасалады.

## Windows installer build

Репозиторий GitHub Actions-қа қосылғанда `.github/workflows/build-windows.yml` workflow-ын `Actions → Build QorBackup for Windows → Run workflow` арқылы іске қосуға болады. Ол `windows-latest` runner ішінде Rust, WebView2 және Windows bundler арқылы x64 `.exe` NSIS installer мен `.msi` файл жасап, оларды workflow artifact ретінде береді.

Бұл sandbox ARM Linux болғандықтан Windows executable-ді осы ортада тікелей іске қосып жинау мүмкін емес. Windows workflow-ы сол шектеуді айналып өтіп, бірдей source code-тан дайын installer шығарады.

## Келесі development кезеңі

Қазіргі backup progress mock режимінде. Нағыз өнім үшін native folder watcher, файл өзгерісін анықтау, chunk upload, AES-256 шифрлау, S3-compatible storage және restore worker қосылады.

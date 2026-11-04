# QorBackup MVP — жұмыс статусы

## 1. Dashboard shell және қазақша визуалдық жүйе
- [x] Sidebar арқылы «Шолу», «Файлдар», «Backup тарихы» және «Баптаулар» бөлімдері арасында desktop-style навигация жұмыс істейді.
- [x] Интерфейс таза, заманауи және сенімді dashboard тәжірибесі ретінде қазақ тіліндегі мәтіндермен жасалған.
- [x] Backup статусы, соңғы backup уақыты және storage қолданылуы шолу экранында көрінеді.

## 2. Backup көздерін басқару
- [x] Пайдаланушы mock folder picker әрекеті арқылы backup жасалатын папка қоса алады.
- [x] Таңдалған файлдар мен папкалардың тізімі, көлемі және файл саны көрсетіледі.
- [x] Қосылған папканы тізімнен алып тастау әрекеті бар.

## 3. Backup flow
- [x] Негізгі backup батырмасы интерактивті mock синхрондауды бастайды.
- [x] Синхрондау барысы пайызбен және progress күйімен көрсетіледі.
- [x] Орындалып жатыр, сәтті аяқталды және қате/қолжетімсіз әрекет feedback күйлері қарастырылған.
- [x] Сәтті backup аяқталғаннан кейін соңғы backup уақыты мен activity жаңарады.

## 4. Backup тарихы және restore
- [x] Backup тарихында күн, көлем, файл саны және нәтиже статусы көрсетіледі.
- [x] Тарихтағы әр backup нұсқасы үшін mock restore әрекеті бар.
- [x] Restore басылғанда toast арқылы түсінікті confirmation feedback көрсетіледі.

## 5. Desktop application foundation
- [x] Tauri 2 shell, Rust entrypoint және Windows/macOS/Linux bundle конфигурациясы қосылды.
- [x] Tauri ішінде native folder picker, ал браузер Preview-де fallback mock picker жұмыс істейді.
- [x] Windows x64 `.exe`/`.msi` шығаратын GitHub Actions workflow қосылды.
- [ ] Native folder watcher, файлдарды chunk арқылы жіберу және нақты backup worker қосу.
- [ ] S3-compatible storage, chunk upload және шифрлау backend-ін қосу.
- [ ] Authentication және database-backed backup history енгізу.

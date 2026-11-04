# QorBackup MVP жоспары

## Өнім мақсаты
QorBackup — болашақ Tauri desktop backup қосымшасына негіз болатын қазақ тіліндегі қауіпсіз әрі түсінікті backup dashboard прототипі. MVP нақты файл сақтау backend-іне тәуелді болмайды: пайдаланушы backup жасалатын папкаларды таңдап, синхрондау процесін mock ретінде көре алады және backup тарихынан restore әрекетін іске қоса алады.

## Қамту аймағы
- Desktop-style web интерфейс: sidebar, topbar және негізгі dashboard.
- Бөлімдер: Шолу, Файлдар, Backup тарихы, Баптаулар.
- Статус карталары: қорғаныс күйі, соңғы backup, storage қолданылуы, сақталған файлдар.
- Mock folder picker арқылы backup көзіне папка қосу және алып тастау.
- Backup бастау батырмасы, пайыздық прогресс, аяқталу/қате/орындалу күйлері.
- Backup тарихы: күні, көлемі, файл саны және нәтиже статусы.
- Mock restore: тарихтағы нұсқаны қалпына келтіру туралы feedback.
- Responsive layout: desktop-та тұрақты sidebar, шағын экранда ықшам навигация.

## Дизайн бағыты
Үш ықтимал стиль:
1. **Precision utility** — 0.07: кәсіби backup құралына тән тығыз, техникалық интерфейс.
2. **Quiet confidence** — 0.06: жылы қағаз түсті фон, қою көк-жасыл мәтін, сабырлы әрі сенімді визуал.
3. **Neo-cloud** — 0.04: ашық түсті карточкалар, көк акцент және көбірек gradient.

Таңдалған стиль: **Quiet confidence**.

- **Design Movement:** calm productivity software, editorial dashboard және скандинавиялық функционализмнің үйлесімі.
- **Core Principles:** ақпарат иерархиясы анық; негізгі әрекет бірден көрінеді; бос кеңістік дем береді; әр статус нақты және қысқа жазылады.
- **Color Philosophy:** warm ivory фон қауіпсіздік пен тыныштық сезімін береді; deep ink мәтін оқылымды етеді; moss/teal акцент backup-тың тірі әрі сау күйін көрсетеді; coral тек назарды қажет ететін әрекеттерге жұмсалады.
- **Layout Paradigm:** сол жақтағы тұрақты control rail және оң жақтағы жұмыс canvas-ы; ортасында үлкен hero card, төменде кезекпен орналасқан activity/table блоктары. Барлық бөлімдер бірдей grid-ке қамалмайды.
- **Signature Elements:** «қалқан + бұлт» монограммасы; progress сақинасы; карточкалардың сол жақ edge-індегі status rail.
- **Interaction Philosophy:** backup іске қосылғанда интерфейс тыныш қалады, progress нақты қозғалады, ал toast қысқа әрі сенімді feedback береді. Әр mock әрекет undo/қайта іске қосуға түсінікті.
- **Animation:** 180–240ms ease-out hover/press; progress 1000ms linear; статус өзгергенде subtle fade/slide; артық bouncing жоқ.
- **Typography System:** Inter жүйелік sans fallback; display 28–36px semibold, section 15–18px semibold, body 13–14px; цифрларда tabular-nums.
- **Brand Essence:** маңызды файлдарды жоғалтпайтын сабырлы backup көмекшісі; сенімді, жинақы, қамқор.
- **Brand Voice:** тақырыптар сабырлы және нақты. Мысал: «Файлдарыңыз бақылауда», «Келесі backup-қа дайынсыз ба?».
- **Wordmark & Logo:** Q әрпін қалқан ішіндегі split-path ретінде көрсету; mark жеке, атауы жанында.
- **Signature Brand Color:** қою көк-жасыл `#155e59` — QorBackup-тың тұрақтылық пен қорғанысты білдіретін негізгі түсі.

## Техникалық тәсіл
- React + TypeScript + Tailwind негізіндегі дайын web-db-user starter.
- Нақты серверлік backup орнына component state және interval арқылы mock flow.
- Lucide icons және starter UI Button қолдану.
- Кейін Tauri shell, native folder watcher, chunk upload және S3 storage қосуға ыңғайлы айқын компонент құрылымы.
- `/manus-routes.json` арқылы route manifest сақтау.

## Жоба құрылымы
- `client/src/pages/Home.tsx`: dashboard layout, navigation және MVP интеракциялары.
- `client/src/index.css`: quiet-confidence theme, responsive layout және custom component styles.
- `client/src/App.tsx`: негізгі route.
- `client/index.html`: тіл, title және document metadata.
- `public/manus-routes.json`: қолданба беттерінің manifest-і.
- `TODO.md`: орындалу статусы.

## Келесі кезең
MVP интерфейсі бекітілген соң Tauri wrapper, native folder watcher, managed storage, auth және database-backed backup history кезең-кезеңімен қосылады.

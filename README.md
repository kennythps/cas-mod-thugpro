# CAS Mod v2 — THUG Pro

**[Русский](#русский) · [English](#english)**

---

## Русский

Мод для **Tony Hawk's Underground Pro**, который открывает в редакторе персонажа то, что игра
прятала: отдельные мужские и женские модели частей тела, «ped»-модели NPC, отдельные пункты цвета
почти для всего и предупреждения о крашах прямо в названиях пунктов меню.

Мод меняет **один скрипт из четырёх** в архиве `Skateshop_scripts.prx`. Остальные три —
`skateshop.qb`, `skateshop_scripts.qb` и `colormenu.qb` — остаются байт в байт такими же,
как в игре. Это делает мод одним из самых безопасных для установки: вы получаете новые
возможности редактора и не откатываете ничего другого.

### Что меняется

#### 1. Мужские и женские части разделены

В ванили половина пунктов редактора была общей на оба пола, и игра сама подставляла нужную
модель. Мод разводит их на явные пункты:

| Ваниль | Мод |
|---|---|
| `Ped Heads` | `Ped Head Male`, `Ped Head Female` |
| `Hair` | `Hair Male`, `Hair Female` |
| `Hair Color` | `Hair Male Color`, `Hair Female Color` |
| `Hat Hair` | `Hat Hair Male`, `Hat Hair Female` |
| `Hat Hair Color` | `Hat Hair Male Color`, `Hat Hair Female Color` |
| `Shirt Style` | `Shirt Style Male`, `Shirt Style Female` |
| `Shirt Color` | `Shirt Male Color`, `Shirt Female Color` |
| `Shirt Sleeves Color` | `Shirt Sleeves Male Color`, `Shirt Sleeves Female Color` |
| `Gloves` | `Gloves Male`, `Gloves Female` |
| `Gloves Color` | `Gloves Male Color`, `Gloves Female Color` |
| `Pants` | `Pants Male`, `Pants Female` |
| `Pants Color` | `Pants Male Color`, `Pants Female Color` |

Пункты раскрашены по цветам, чтобы различать группы с первого взгляда.

#### 2. Открыты «ped»-модели

В ванили доступны только два педовских персонажа — `ped_m_head` и `ped_f_head`. Мод добавляет
ещё семь, обычно недоступных в редакторе:

```
ped_body            ped_m_torso          ped_f_torso
ped_m_accessories   ped_f_accessories
ped_m_legs          ped_f_legs
```

Это тела, торсы, аксессуары и ноги NPC — можно собрать персонажа из кусков городской толпы.

#### 3. Предупреждения о крашах в названиях

Самое практичное: у каждого проблемного «ped»-пункта в названии указан диапазон моделей,
на которых игра падает. Раньше это выяснялось только методом тыка и вылета.

| Пункт меню | Краш на моделях |
|---|---|
| Ped Body | 90–101 |
| Ped Torso Male | 46–52 |
| Ped Torso Female | 14–15 |
| Ped Accessories 1 | 21–25 |
| Ped Accessories 2 | только на 4 |
| Ped Legs Male | 43–49 |
| Ped Legs Female | 13–14 |

Диапазоны выведены и в полном названии пункта, и в заголовке открывшегося меню — чтобы
не забыть, пока листаешь модели.

#### 4. Отдельные пункты цвета

К каждой новой части добавлен свой пункт цвета, а не общий на группу:
`Ped Body Color`, `Ped Torso Male Color`, `Ped Torso Female Color`, `Ped Accessories 1 Color`,
`Ped Accessories 2 Color`, `Ped Legs Male Color`, `Ped Legs Female Color`, `Head Color`,
`Hair Male/Female Color`, `Hat Hair Male/Female Color`, `Shirt Male/Female Color`,
`Shirt Sleeves Male/Female Color`, `Gloves Male/Female Color`, `Pants Male/Female Color`,
`Body Color`, `Shoelace Color`.

#### 5. Оформление

- Заголовок меню редактора заменён с `Edit Skater` на `CAS Mod v2` (три места: меню входа,
  меню редактирования и меню опций).
- В меню `Information` добавлен блок кредитов: `CAS Mod v2`, `Made by ken`,
  `THPS CIS / DOC THPS`, дата `30.10.2023`.

#### 6. Чего мод НЕ добавляет

Чтобы не приписывать лишнего: масштабирование частей (`Scaling`), стикеры, свой рисунок деки
и иконки были в игре и до мода. Мод их не трогает. Татуировки тоже были, но в моде к ним
добавлены варианты настройки.

### Установка

1. Скачайте архив мода из раздела **Releases**.
2. Сделайте бэкап папки `data\pre\` вашей установки THUG Pro.
3. Скопируйте `data\pre\Skateshop_scripts.prx` в `<THUG Pro>\data\pre\`, согласившись на замену.
4. Запустите игру и откройте редактор персонажа — заголовок должен читаться как `CAS Mod v2`.

### Про `updt.dll`

В пакете лежат два варианта этой библиотеки — это D3D9-прокси, который THUG Pro использует
как загрузчик обновлений.

| Файл | Что делает |
|---|---|
| `updt.dll` (в корне пакета) | Адрес манифеста обновлений заменён заглушкой — апдейтер не может получить манифест и **не перезапишет мод** |
| `turn on thug pro update system\updt.dll` | Настоящий апдейтер (`dl.thugpro.com`) — для тех, кто хочет вернуть автообновление |

Без первого варианта автообновление при запуске вернуло бы ванильные скрипты, и мод бы просто исчез.
Это не вирус и не что-то скрытое — обычная защита мода от затирания. Если сомневаетесь,
не копируйте `updt.dll` вовсе: мод будет работать, но обновления игры смогут его снести.

### Совместимость

Хорошая новость: мод собран на той же версии THUG Pro, что стоит у большинства игроков сегодня.
Архив мода — 98 840 байт, актуальный `Skateshop_scripts.prx` в установке — 105 868 байт,
и внутри обоих лежат **одни и те же четыре скрипта**.

Сравнение по содержимому:

| Скрипт | Совпадает с ванилью |
|---|---|
| `levels\skateshop\skateshop.qb` | да, байт в байт |
| `levels\skateshop\skateshop_scripts.qb` | да, байт в байт |
| `levels\skateshop\colormenu.qb` | да, байт в байт |
| `levels\skateshop\skateshop_cas.qb` | **нет — это и есть мод** |

То есть установка меняет ровно один скрипт и не откатывает ничего постороннего.
В отличие от модов, собранных на старых билдах, здесь нет риска получить расхождение
с хостом из-за чужих скриптов.

Единственная оговорка: если разработчики THUG Pro когда-нибудь обновят
`Skateshop_scripts.prx`, установка этого мода вернёт `skateshop_cas.qb` к версии 2023 года.
Бэкап `data\pre\` решает вопрос за пять секунд.

### Как это было собрано

Скрипты THUG Pro лежат в `.prx`-архиве в скомпилированном виде (QB-байткод), поэтому правка
делается в три шага:

1. **Декомпиляция.** `skateshop_cas.qb` из архива → текстовый исходник `skateshop_cas.txt`
   (3 947 строк, 83 функции). Использовался `roqq.exe -d`; рядом должна лежать
   `skateshop_cas.qb_table.qbi` — таблица QB-ключей (708 записей), иначе вместо имён
   читаются хеши.
2. **Правка.** В `skateshop_cas.txt` перестроены меню частей: добавлены пункты, разделены
   мужские и женские модели, вписаны предупреждения о крашах, переименованы заголовки.
   Дифф к ванили: **520 добавленных строк, 49 удалённых**.
3. **Сборка.** `roqq.exe -c skateshop_cas.txt` → `skateshop_cas.qb`, затем `PreTool.exe`
   открывает `Skateshop_scripts.prx`, находит `levels\skateshop\skateshop_cas.qb`,
   делает `Replace` и сохраняет архив.

Проверки, которые подтверждают, что в релизе лежит именно этот исходник:

- `roqq.exe -c skateshop_cas.txt` даёт файл **50 986 байт, SHA256 `C893434D…A8C003`** —
  байт в байт совпадает с `skateshop_cas.qb` внутри релизного `.prx`.
- Декомпиляция ванильного `skateshop_cas.qb` (58 452 байта) и файла из релиза даёт
  **3 477 и 3 948 строк**; различия укладываются в 110 участков, 103 из которых — внутри
  функции `create_part_cas_scale_menu` (гигантский построитель меню).
- Таблица ключей, сгенерированная из ванильного `.qb`, **байт в байт совпадает** с таблицей
  из мода: новых QB-ключей мод не вводит, только переставляет существующие.
- Внутренняя запись архива сообщает несжатый размер **50 986** — ровно размер релизного
  `skateshop_cas.qb`.

### Кредиты

- **kennythps** — декомпиляция, правка меню, сборка и упаковка.
- **THPS CIS / DOC THPS** — сообщество, в котором мод делался и тестировался.

Инструменты, которыми это собиралось, написаны не нами и в репозиторий не входят:
`PreTool.exe` (Alabaster, Inc., 2011) — редактор `.prx`/PRE; `roq cmd.exe` (2007) и
`roqo.exe` — GUI-обёртки; `roqq.exe` (2017) — компилятор/декомпилятор QB.
Спасибо их авторам: без них модов на THUG Pro просто не существовало бы.

### Файлы в репозитории

```
skateshop_cas.txt             исходник скрипта целиком (3 947 строк) — главный артефакт
skateshop_cas.qb_table.qbi    таблица QB-ключей, нужна для компиляции и декомпиляции
README.md                     этот файл
LICENSE                       MIT
```

Скомпилированный `skateshop_cas.qb` и готовый `Skateshop_scripts.prx` в git не хранятся —
они прикреплены к релизу. Так репозиторий остаётся лёгким, а диффы читаемыми.

### Лицензия

MIT — см. [LICENSE](LICENSE). Берите, меняйте, форкайте, выкладывайте свои сборки.
Исходные скрипты THUG Pro принадлежат их правообладателям; здесь распространяется
только изменённый скрипт редактора и текст, описывающий его.

---

## English

A mod for **Tony Hawk's Underground Pro** that unlocks what the create-a-skater editor was
hiding: separate male and female part models, NPC "ped" models, a dedicated colour entry for
almost everything, and crash warnings printed right in the menu labels.

The mod changes **one script out of four** inside `Skateshop_scripts.prx`. The other three —
`skateshop.qb`, `skateshop_scripts.qb` and `colormenu.qb` — stay byte-for-byte identical to the
game's own copies. That makes it one of the safest mods to install: you get new editor features
and nothing else is rolled back.

### What changes

#### 1. Male and female parts are split

In vanilla, half of the editor entries were shared between both sexes and the game picked the
right model on its own. The mod makes them explicit:

| Vanilla | Mod |
|---|---|
| `Ped Heads` | `Ped Head Male`, `Ped Head Female` |
| `Hair` | `Hair Male`, `Hair Female` |
| `Hair Color` | `Hair Male Color`, `Hair Female Color` |
| `Hat Hair` | `Hat Hair Male`, `Hat Hair Female` |
| `Hat Hair Color` | `Hat Hair Male Color`, `Hat Hair Female Color` |
| `Shirt Style` | `Shirt Style Male`, `Shirt Style Female` |
| `Shirt Color` | `Shirt Male Color`, `Shirt Female Color` |
| `Shirt Sleeves Color` | `Shirt Sleeves Male Color`, `Shirt Sleeves Female Color` |
| `Gloves` | `Gloves Male`, `Gloves Female` |
| `Gloves Color` | `Gloves Male Color`, `Gloves Female Color` |
| `Pants` | `Pants Male`, `Pants Female` |
| `Pants Color` | `Pants Male Color`, `Pants Female Color` |

Entries are colour-coded so the groups are distinguishable at a glance.

#### 2. "Ped" models unlocked

Vanilla exposes only two NPC heads — `ped_m_head` and `ped_f_head`. The mod adds seven more that
are normally unreachable in the editor:

```
ped_body            ped_m_torso          ped_f_torso
ped_m_accessories   ped_f_accessories
ped_m_legs          ped_f_legs
```

Bodies, torsos, accessories and legs taken from the city crowd — enough to build a character out
of NPC pieces.

#### 3. Crash ranges in the labels

The most practical part: every problematic "ped" entry carries the model range that crashes the
game. Previously you found those by trial and error, one hard freeze at a time.

| Menu entry | Crashes on models |
|---|---|
| Ped Body | 90–101 |
| Ped Torso Male | 46–52 |
| Ped Torso Female | 14–15 |
| Ped Accessories 1 | 21–25 |
| Ped Accessories 2 | only 4 |
| Ped Legs Male | 43–49 |
| Ped Legs Female | 13–14 |

The ranges appear both in the full menu label and in the title of the submenu that opens, so they
stay visible while you scroll.

#### 4. Dedicated colour entries

Every new part gets its own colour entry rather than sharing one per group:
`Ped Body Color`, `Ped Torso Male Color`, `Ped Torso Female Color`, `Ped Accessories 1 Color`,
`Ped Accessories 2 Color`, `Ped Legs Male Color`, `Ped Legs Female Color`, `Head Color`,
`Hair Male/Female Color`, `Hat Hair Male/Female Color`, `Shirt Male/Female Color`,
`Shirt Sleeves Male/Female Color`, `Gloves Male/Female Color`, `Pants Male/Female Color`,
`Body Color`, `Shoelace Color`.

#### 5. Presentation

- The editor's menu title changes from `Edit Skater` to `CAS Mod v2` in three places: the entry
  menu, the edit-skater menu and the options menu.
- The `Information` menu gains a credits block: `CAS Mod v2`, `Made by ken`,
  `THPS CIS / DOC THPS`, dated `30.10.2023`.

#### 6. What the mod does NOT add

To avoid overclaiming: part scaling, stickers, custom deck graphics and icons all existed before
the mod and are untouched by it. Tattoos also existed already, but the mod adds adjustment
variants for them.

### Installation

1. Download the mod archive from **Releases**.
2. Back up your THUG Pro `data\pre\` folder.
3. Copy `data\pre\Skateshop_scripts.prx` into `<THUG Pro>\data\pre\`, overwriting.
4. Launch the game and open the skater editor — the title should read `CAS Mod v2`.

### About `updt.dll`

The package ships two builds of this library — it is a D3D9 proxy that THUG Pro uses as its
updater stub.

| File | Behaviour |
|---|---|
| `updt.dll` (package root) | The update manifest host is stubbed out, so the updater cannot fetch a manifest and **will not overwrite the mod** |
| `turn on thug pro update system\updt.dll` | The real updater (`dl.thugpro.com`) — for anyone who wants automatic updates back |

Without the first one, the auto-updater would restore vanilla scripts on launch and the mod would
simply vanish. Nothing hidden or malicious about it — it is ordinary protection against being
overwritten. If you would rather not use it, skip `updt.dll` entirely: the mod still works, but a
game update may wipe it.

### Compatibility

Good news: the mod was built on the same THUG Pro version most players are running today. The
mod's archive is 98,840 bytes, the live `Skateshop_scripts.prx` is 105,868 bytes, and both contain
**the same four scripts**.

Content comparison:

| Script | Matches vanilla |
|---|---|
| `levels\skateshop\skateshop.qb` | yes, byte for byte |
| `levels\skateshop\skateshop_scripts.qb` | yes, byte for byte |
| `levels\skateshop\colormenu.qb` | yes, byte for byte |
| `levels\skateshop\skateshop_cas.qb` | **no — this is the mod** |

So installing changes exactly one script and rolls back nothing else. Unlike mods built on older
game builds, there is no risk of a script mismatch with the host in multiplayer.

One caveat: if the THUG Pro developers ever update `Skateshop_scripts.prx`, installing this mod
brings `skateshop_cas.qb` back to its 2023 state. A `data\pre\` backup settles that in five seconds.

### How it was built

THUG Pro's scripts live inside a `.prx` archive as compiled QB bytecode, so editing takes three steps:

1. **Decompile.** `skateshop_cas.qb` from the archive → the text source `skateshop_cas.txt`
   (3,947 lines, 83 functions), using `roqq.exe -d`. `skateshop_cas.qb_table.qbi` (the QB key
   table, 708 entries) has to sit next to it — without it you get raw hashes instead of names.
2. **Edit.** The part menus in `skateshop_cas.txt` were rebuilt: entries added, male and female
   models split apart, crash warnings written into the labels, titles renamed. Diff against
   vanilla: **520 lines added, 49 removed**.
3. **Build.** `roqq.exe -c skateshop_cas.txt` → `skateshop_cas.qb`, then `PreTool.exe` to open
   `Skateshop_scripts.prx`, locate `levels\skateshop\skateshop_cas.qb`, `Replace` it and save the
   archive.

Checks confirming the release really contains this source:

- `roqq.exe -c skateshop_cas.txt` yields **50,986 bytes, SHA256 `C893434D…A8C003`** — byte for
  byte identical to the `skateshop_cas.qb` inside the released `.prx`.
- Decompiling both the vanilla `skateshop_cas.qb` (58,452 bytes) and the released one gives
  **3,477 and 3,948 lines**; the differences fit into 110 hunks, 103 of them inside
  `create_part_cas_scale_menu`, the giant menu builder.
- The key table generated from the vanilla `.qb` is **byte-identical** to the one shipped with
  the mod: the mod introduces no new QB keys, it only rearranges existing ones.
- The archive's internal record reports an uncompressed size of **50,986** — exactly the size of
  the released `skateshop_cas.qb`.

### Credits

- **kennythps** — decompiling, menu editing, compiling and packaging.
- **THPS CIS / DOC THPS** — the community where the mod was made and tested.

The tools used here were written by other people and are not part of this repository:
`PreTool.exe` (Alabaster, Inc., 2011) for `.prx`/PRE editing, `roq cmd.exe` (2007) and `roqo.exe`
as GUI wrappers, and `roqq.exe` (2017) as the QB compiler/decompiler. Credit to their authors —
without them there would be no THUG Pro modding at all.

### Repository layout

```
skateshop_cas.txt             the full script source (3,947 lines) — the main artifact
skateshop_cas.qb_table.qbi    QB key table, required to compile and decompile
README.md                     this file
LICENSE                       MIT
```

The compiled `skateshop_cas.qb` and the ready-to-use `Skateshop_scripts.prx` are not tracked in
git — they are attached to the release. That keeps the repository light and the diffs readable.

### License

MIT — see [LICENSE](LICENSE). Take it, change it, fork it, publish your own builds.
The original THUG Pro scripts belong to their respective rights holders; what is distributed here
is the modified editor script and the text describing it.

# KeePassAKO
KeePass Anti-Keylogger Obfuscation
I don't know any programming language. My idea is just for implementation.
Я не знаю ни одного языка программирования. Моя идея предназначена только для реализации.

# KeePassXC/KeePass 2 Anti-Keylogger Obfuscation
**Feature Proposal by SolarSvarga**
🇺🇸 English | 🇷🇺 Русский

---

## 🇺🇸 English {#english}
**Russian text below**

**Hello, KeePassXC/KeePass 2 developers!**

— I propose adding such a feature to Auto-Type in KeePassXC/KeePass 2. When Auto-Type types a password into a browser on a website or any program, it should first insert one character from the password, before/after this real password character, into empty space (virtual space) it inputs a random number of characters from 3 to 39 according to AES standard, then again after this "junk" it inserts the next (second) real password character and after it again generates random symbolic junk into the void (virtual space), and so on after each correct password character until the entire correct password is entered on the site or program. All this should happen without any pauses between entering real password characters and symbolic junk, so that no pattern is detected.

— As a result, a keylogger or any viral program intercepting the password will see giant junk from characters, making the criminal guess where the real password characters are in this mess, which will take him millions of years.

— NO need for Auto-Type in KeePassXC/KeePass 2 to simulate human keystrokes for the entire text, but simply paste the main password into the browser and program field, and insert a random set of characters after each password character into empty virtual space during the entire process.

**For example:**
Password "MYPASSWORD" will look like this:
xxxMxxxYxxxPxxxAxxxSxxxSxxxWxxxOxxxRxxxDxxx

**Translated with AES system like this:**
T:3v=$M#S9=:zY4%:=EmPr5.&Z=AT3.d>#S<aF7;~S9$f:>YW3dA!;~O%4.?vZRp3*:&TD*$kS,2

**Breakdown of each letter for clarity:**
T:3v=$ -M- #S9=:z -Y- 4%:=Em -P- r5.&Z= -A- T3.d># -S- <aF7;~ -S- 9$f:>Y -W- 3dA!;~ -O- %4.?vZ -R- p3*:&T -D- *$kS,2.

Naturally, it's not necessary for all junk characters to be in the same quantity; they will have random quantity and character sets.

**Full algorithm (exactly as intended):**
1. Take the real password: "MYPASSWORD"
2. Paste only real characters into the password field: "MYPASSWORD"
3. INTO EMPTY virtual space after EACH character add 3-39 character junk
4. KeePassXC/KeePass 2 pastes everything at once into the input field on the site, game, or program, simultaneously into the empty (virtual field) field a set of random characters without delays between junk and real password characters.
5. The site server receives the clean password, while the attacker gets a giant password.
6. Keylogger catches password + mega-junk
7. Even if the attacker sees via screenshot that the password in the site field is shorter than what he got, it still won't help him anyway.

**What each participant sees:**
Site: MYPASSWORD  
Keylogger: M{20 characters}Y{15 characters}P{28 characters}A{12 characters}S{35 characters}S{19 characters}W{24 characters}O{17 characters}R{3 characters}D{7 characters}

**Advantages:**
- Fast input time since keystroke simulation is not used.
- Each password character protected by individual 3-39 character junk  
- Keylogger gets giant character set
- Phishing automatically gets junk characters
- Even RAM encryption not needed — junk is the protection, as no one will see the needed password in this mess.
- Universal for all forms (passwords/cards/2FA)

This might be a revolutionary solution to the keylogger problem through simple paste with smart junk character porridge after each password character.

**Author of the proposal:** SolarSvarga [https://github.com/solarsvarga](https://github.com/solarsvarga)
I haven't seen exactly this solution anywhere.

## 🇷🇺 Русский {#русский}

**Привет, разработчики KeePassXC/KeePass 2!**

— Предлагаю добавить такую фичу в Auto-Type в KeePassXC/KeePass 2. Когда Auto-Type печатает пароль в браузере на сайте или в какой-либо программе, он должен сначала вставлять один символ из пароля, до/после этого реального символа из пароля, в пустое место (виртуальное пространство) вводит рандомное количество символов от 3 до 39 по стандарту AES, потом снова после этого "мусора" он опять вставляет следующий (второй) настоящий символ пароля и за ним опять делает рандомный символьный мусор в пустоту (в виртуальное пространство), и так после каждого правильного символа из пароля, пока весь верный пароль не введётся на сайте или в программе. Всё это должно происходить без всяких пауз между вводами настоящих символов из пароля и символьным мусором, чтобы не была обнаружена закономерность.

— В итоге кейлоггер или любая вирусная программа при перехвате пароля увидит гигантский мусор из символов, из-за чего преступнику придётся гадать, где же настоящие символы реального пароля в этой каше, на что он потратит миллионы лет.

— НЕ нужно, чтобы Auto-Type в KeePassXC/KeePass 2 симулировал человеческие нажатия для всего текста, а просто вставил весь основной пароль в поле браузера и программы, а рандомный набор символов после каждого символа из пароля вставлял в пустое виртуальное пространство во время всего процесса.

**К примеру:**
Пароль "MYPASSWORD", будет выглядеть вот так:
xxxMxxxYxxxPxxxAxxxSxxxSxxxWxxxOxxxRxxxDxxx

**В переводе вот так с системой AES:**
T:3v=$M#S9=:zY4%:=EmPr5.&Z=AT3.d>#S<aF7;~S9$f:>YW3dA!;~O%4.?vZRp3*:&TD*$kS,2

**Расшифровка каждой буквы для наглядности:**
T:3v=$ -M- #S9=:z -Y- 4%:=Em -P- r5.&Z= -A- T3.d># -S- <aF7;~ -S- 9$f:>Y -W- 3dA!;~ -O- %4.?vZ -R- p3*:&T -D- *$kS,2.

Естественно, не обязательно, чтобы все мусорные символы находились в одинаковом количестве, они будут с рандомным количеством и набором символов.

**Полный алгоритм работы (точно как задумано):**
1. Берём реальный пароль: "MYPASSWORD"
2. В поле пароля вставляем только настоящие символы: "MYPASSWORD"
3. В ПУСТОЕ виртуальное пространство** после КАЖДОГО символа добавляем кашу 3-39 символов
4. KeePassXC/KeePass 2 вставляет всё разом в поле ввода данных на сайте, игре или в программе, одновременно в пустое (виртуальное поле) поле набор из случайных символов без задержек между мусором и реальными символами паролей.
5. Сервер сайта получает чистый пароль, а злоумышленник гигантский пароль.
6. Кейлоггер ловит пароль + мега-мусор
7. Даже, если злоумышленник увидит через скриншот, что пароль в поле сайта меньше, чем он получил, то в любом случае это ему не поможет.

**Что видит каждый участник:**
Сайт: MYPASSWORD  
Кейлоггер: M{символов 20}Y{символов 15}P{символов 28}A{символов 12}S{символов 35}S{символов 19}W{символов 24}O{символов 17}R{символов 3}D{символов 7}

**Преимущества:**
- Время ввода быстрое, так как не используется симуляция нажатия.
- Каждый символ пароля защищён индивидуальным мусором 3-39 символов  
- Кейлоггер получает гигантский набор символов
- Фишинг автоматически получит мусор из символов
- Даже шифрование RAM не нужно — мусор и есть защита, так как никто в этой каше не увидит нужный пароль.
- Универсально для всех форм (пароли/карты/2FA)

Возможно, это революционное решение проблемы кейлоггеров через простую вставку с умной кашей из символов после каждого символа от пароля.

**Автор предложения:** SolarSvarga https://github.com/solarsvarga
Прям в точности такое решение не видел ни у кого.

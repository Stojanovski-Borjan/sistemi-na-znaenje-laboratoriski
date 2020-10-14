# Вежби - TF-IDF

## Задача 1 - Класификација на спам кометари со tf-idf карактеристики и дрво на одлука
Дадено е податочно множество на коментари на Youtube видеа од музичкиот изведувач Еминем. Секој од коментарите припаѓа на една од класите "ham" или "spam". Поделете го податочното множество на множество за тренирање, во кои ќе се вклучат првите 75% од податочното множество, и множество за тестирање со останатите инстанци од податочното множество.

Изградете модел на дрво на одлука за класификација на коментарите со тренирачкото множество, каде што карактеристиките за секој коментар ќе бидат добиени од зборовниот вектор креиран со td-idf. Пресметајте точност, одзив и прецизност на моделот со тестирачкото множество и испринтајте ги вредностите на стандарден излез. Дополнително од стандарден влез се чита еден нов коментар во променливата test_comment. Предвидете ја класата на овој коментар и испринтајте ја.

Напомена: Вокабуларот на тест множеството треба да биде исто како и тренирачкото множество.

точност = (TP + TN) / (TP + FP + TN + FN)

прецизност = TP / (TP + FP)

одзив = TP / (TP + FN)
TP - број на точно предвидени спам коментари

FP - број на грешно предвидени спам коментари

TN - број на точно предвидени хам коментари

FN - број на грешно предвидени хам коментари



### Sample Input  &#8594; Expected output
##### Case 1.)
Input: eminem new song check out my videos\
Output:\
Tochnost: 0.918918918918919\
Preciznost: 0.96\
Odziv: 0.8727272727272727\
spam


##### Case 2.)
Input: it reminds me of a smaller version of 8 mile. Give this guy a chance since everyone has to start somewhere!\
Output:\
Tochnost: 0.918918918918919\
Preciznost: 0.96\
Odziv: 0.8727272727272727\
ham


---
## Задача 2 - Најслични документи според клучни зборови
Дадено е податочно множество на документи од спорт (спорт) и наука (science). Потребно е да се најдат најсличните 4 документи на документ кој се чита од стандарден влез (test_doc). Сличноста на документите се одредува според клучни зборови пронајдени со методот tf-idf, односно сличноста се однесува на бројот на заеднички клучни зборови. Колку е поголем бројот на заеднички клучни зборови, толку тој документ е посличен со моменталниот документ.

Секој од документите треба да се престави со tf-idf вектор, од кој треба да се извлечат зборовите со tf-idf вредност поголема од 0 како клучни зборови. За документот кој се чита од стандарден влез потребно е да се извлечат клучните зборови и да се спореди со документите од податочното множество (да се најде бројот на заеднички клучни зборови). На стандарден излез испечатете ги индексите на 4те најслични документи од множеството за тренирање, како и заедничните клучни зборови (сортирани алфабетски).

### Sample Input  &#8594; Expected output
##### case 1.)
Input: """Kobe Bryant once scored 80+ points in only three quarters. They’re also, for the first time this season, the proud owners of a ten-game winning streak. On top of that, you may have heard, Kobe Bryant passed Michael Jordan on Sunday evening to move into third place on the NBA’s all-time scoring list. """\
Output: \
Dokument #8: all also bryant evening first for game have heard into jordan kobe list may michael move nba owners passed place proud scoring season streak sunday that they third this three time top winning you\
Dokument #2: first for have ten that this time\
Dokument #5: all for have into they this\
Dokument #11: all for game sunday that three


##### case 2.)
Input: "The BLS reports that the median annual salary for athletic trainers was $44,670 per year in 2015, and that those working in business, professional, labor, political or other organizations earned the highest average annual wage."\
Output: \
Dokument #0: and for that was\
Dokument #4: and for those year\
Dokument #11: and for that was\
Dokument #2: and for that

---
## Задача 3 - Класификација на коментари според најслични коментари
Дадено е податочно множество (dataset) на спам коментари. Потребно е да се направи класификатор на коментари според tf-idf векторските репрезентации на коментарите. Овој класификатор ја предвидува класата на моменталниот коментар според класата која е мнозинство од класите на N-те најслични коментари претставени со tf-idf вектори.

Од стандарден влез се чита бројот на слични коментари N во променливата n, како и коментар кој треба да се класифицира во spam или ham класа. За да се предвиди класата, најпрво потребно е да се најдат n најслични коментари според косинусно растојание, по што класата треба да се определи според доминантната класа од множеството на класи добиени од најсличните коментари. Ако не се пронајдени N најслични документи со сличност поголема од 0, потребно е да се разгледуваат само добиените најслични документи (чиј што број е помал од N). Доколку бројот на двете класи е еднаков треба да се предвиди класата spam.

### Sample Input  &#8594; Expected output
##### case 1.)
Input: 5\
eminem new song check out my videos\
Output: \
Predvidenata klasa e spam so 5/5 glasovi.

##### case 2.)
Input: 15\
it reminds me of a smaller version of 8 mile. Give this guy a chance since everyone has to start somewhere!\
Output: \
Predvidenata klasa e spam so 10/15 glasovi.

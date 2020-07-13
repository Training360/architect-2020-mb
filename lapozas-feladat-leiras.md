# Lapozás - Feladatleírás (házi feladat)

Annyira tetszett Berni példája a lapozással kapcsolatban, hogy 
feldolgoztam házi feladatként, egy kicsit átszabva. Az alapvető probléma 
az, hogy a felhasználó lapozgat egy táblázatot, de közben a háttérben az 
adatok módosulnak.
 
Adott tehát egy alkalmazás, REST felülettel, mely alkalmazottak
nyilvántartását végzi.

A `/api/employees` címen `GET` metódussal visszaadja az alkalmazottakat,
míg a `POST` metódussal egy új alkalmazottat lehet felvenni.

A lekérdezésnél egy paraméterrel lehet szűrni, hogy csak azokat az 
alkalmazottakat adja vissza, akik nevében szerepel a paraméterként
átadott karakterlánc.

Ki lehet indulni a `employees` könyvtárban található alkalmazásból.

Az alkalmazás működésével kapcsolatban a következők 
az elvárások:

* A felhasználó le tudja kérni az alkalmazottak listáját.
* Meg tudjon adni egy szűrő paramétert.
* Tudjon lapozni. Amennyiben a lapozás közben oldalt vált,
akkor azokat az adatokat lássa, melyek aktuálisak voltak az
alkalmazottak listájának **első** lekérdezésekor.
* A felhasználó kapjon értesítést, ha változott a háttérben az adat.
Csak az a felhasználó kapjon, akinek a lekérdezésének eredményében tényleg
változott az adat.
* Készülj fel arra, hogy az alkalmazást horizontálisan skálázni lehessen!
* A megoldás ne lassuljon az adatok növekedésével!
* Java EE alkalmazás legyen, WildFly-jal, Postresql adatbázissal!

Az első feladat **csak** annyi, hogy tervezd meg az alkalmazást! Később fogjuk 
implementálni.

* Milyen eszközöket használnál a tervezéshez, és a terveid másokkal
való megosztásához?
* Hogyan terveznéd meg az API-t? Hogyan változtatnád meg az URL-eket,
paramétereket, stb.? Hogyan küldenéd be a szűrő feltételt? Milyen
 struktúrát adnál vissza? Hogyan írnád le pontosan az API-t?
* Hol tárolnád az egy lekérdezéshez tartozó adatokat? Egyszerre
mennyi adatot tárolnál? Mik ezeknek az előnyei/hátrányai?
* Milyen komponenseket (osztályokat) használnál? Milyen függőségben lennének ezek
egymással? Ábrázold! Biztos nincs körkörös függőség?
Kb. tervezd meg a hívási láncot, és az átadott paramétereket!
* DeltaSpike hogyan kezeli a lapozást?
* Hogyan oldanád meg a vízszintes skálázhatóságot?
* Hogyan oldanád meg, hogy az implementációd cserélhető legyen?
* Hogyan oldanád meg, hogy a felhasználó lapozáskor értesítést kapjon arról,
hogy változott az adat?
* Hogyan oldanád meg, hogy a felhasználó az adatváltozáskor **azonnal**
kapjon értesítést? Megzavarja ez a technológia a függőséget (nem keletkezik
kör)?
* Milyen szabványt használsz a hibák megjelenítésére REST-en?
* A WildFly milyen könyvtárat használ a REST webszolgáltatások
implementálására, valamint a objektumok JSON formátumba való
szerializálására? Hogyan adod meg, hogy a dátumokat ISO 8601
formátumban írja ki? Milyen függőségeket kell használnod?
Nem kerül be ezáltal felesleges jar fájl a war állományba?
Hogyan szabadulsz meg a felesleges függőségektől?



 
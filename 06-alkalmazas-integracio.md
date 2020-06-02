# Integrációs technológiák

## XML, SOAP

* Mire való a névtér?
* Mi az az XML séma? Vivel definiált az XML séma?
* Mire való az XPath? Milyen részekből áll? Hol használható?
* Milyen XML eszközöket ismersz?
* Mire való az XSLT?
* Java-ban milyen API-k vannak XML kezelésre? Mi része a standard Javanak? Milyen különbségek vannak köztük?
* Mi az az XML entity reference?
* Mi az az XML bomb?
* Mi az a CDATA?
* Mikor elem, mikor attribútum?
* Vannak-e elnevezési konvenciók?
* Hogyan tesztelsz XML feldolgozást?
* Milyen szabványokat ismert SOAP webszolgáltatásokra Java-ban? Milyen implementációkat?
* Kód- és sémagenerálás mennyire elfogadható?
* Hogyan akadáloyzzuk meg, hogy a teljes XML betöltésre kerüljön?
* SOAP/WSDL lehetővé teszi, hogy egymással kommunikálni tudjanak eltérő technológiák?

### Említendő

* Four Tenets of SOA
	* Boundaries Are Explicit: tiszta és egyszerű API, tipikusan durva szemcsézettségű
	* Services Are Autonomous: laza kapcsolat, ne kelljen az operációkat meghatározott sorrendben meghívni, nem hagyhatja egy operáció inkonzisztens állapotban, tipikusan egy tranzakciónyi egy operáció
	* Services Share Schema and Contract, Not Class: black box, csak az interfészleírás (WSDL) megosztott
	* Service Compatibility is based on Policy: kommunikáció szabályai deklarálandók, WS-Policy írja le a szabályokat, pl. security, quality of service

SOAP stílus, kódolás:

* Stílus
    * RPC-stílus
    * Document stílus
* Kódolás
    * Literal-kódolás
    * SOAP-kódolás = encoded
* Paraméter
    * Unwrapped (bare)
    * Wrapped
* Leggyakrabban használt: Document/literal

https://www.ibm.com/developerworks/webservices/library/ws-whichwsdl/


## HTTP, REST

* Mik azok a HTTP státuszkódok, melyek a gyakori státuszkódok?
* Mit hívunk RESTful webszolgáltatásoknak? Milyen tulajdonságai vannak?
* Egyes vagy többesszámot használunk az erőforrások URL-jében?
* Vannak-e típusok a JSON-ben?
* A RESTful webszolgáltatások a HTTP milyen tulajdonságait használják ki?
* RESTful webszolgáltatásoknál mire valók a paraméterek?
* Milyen metódusokkal használjuk a create és update műveleteket?
* A CRUD műveleteknél milyen értékeket adjunk vissza?
* Mi az a `Content-Type` header és Mime-type
* Hogyan néz ki a http cache-elés? Mi az az ETag?
* Milyen megoldásokat ismersz arra, hogy szerver oldalról üzeneteket küldj?
* Mi az a STOMP?
* Mi az a HATEOAS?
* Mi az a CORS?
* Hogyan kezelsz hibákat? RFC 7807
* Van séma JSON-re?
* Van API leírás REST-re?
* Milyen szabványok és implementációk vannak REST implementálásra Java-ban?
* Milyen JSON library-k vannak Java-ban?
* Hogyan kezelsz API verziókat?
* Milyen teszt eszközöket ismersz?

### Említendő

* REST Architectural Constraints
	* Uniform interface: erőforrások, URI-val azonosítva, metódusok, leíró üzenetek, HATEOAS (linkek a részletekre)
	* Client–server: egymástól függetlenek, kliens csak az URL-jét tudja a szervernek
	* Stateless: nincs session (autentikáció - minden kérésben küldeni kell)
	* Cacheable: támogassa a cache-elést akár szerver, akár kliens oldalon
	* Layered system: nem kell a kliens és szerver között közvetlen kapcsolat, más eszközök is beékelődhetnek (security, loadbalancing, stb.)
	* Code on demand (optional): visszaadhat futtatható kódrészleteket
* Richardson Maturity Model
	* Level 0: HTTP használata, gyakorlatilag RPC, HTTP mint transzport
	* Level 1 - Resources: egyedileg azonosított erőforrások
	* Level 2 - HTTP Verbs: HTTP metódusok használata annak jelentése alapján
	* Level 3 - Hypermedia Controls: discoverability, linkek, hogy merre lehet továbbmenni
* OpenAPI
* Postman
* Swagger

## JMS

* Mire való a fejléc?
* Ki lehet olvasni egy üzenetet a sorból, anélkül, hogy kivennénk?
* Mi az a mérgezett üzenet?
* Mi az a correlation id?
* Lehet küldeni és a választ fogadni egy tranzakcióban?
* Mi kell ahhoz, hogy egy tranzakcióban legyen a db írás és az üzenetküldés?
* Mi az a Temporary queue?
* Mire való a message selector?
* Mire való a Message Persistence?
* Hogyan állítható a prioritás?
* Garantálható sorrend az üzenetek között?
* Mi az a Message Expiration és Delivery Delay?

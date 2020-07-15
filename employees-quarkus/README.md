# Employees alkalmazás Quarkus-szal

A projekt a `employees-micro` könyvtárban lévő Thorntailes projekt átültetése
Quarkus keretrendszerre.

Teendők voltak:

* Projekt generálás a https://code.quarkus.io/ oldalon, függőségek:
    * Hibernate ORM with Panache
    * JDBC Driver - PostgreSQL
    * Flyway
    * RESTEasy JSON-B
* További függőségek:
    * MapStruct
    * Lombok 
* Legalább 3.6.1 Maven telepítése
* `EmployeeBean` és `EmployeeResource` az injektált mezők ne privátak legyenek!
Ez sebességhangolás miatt van így.
* Az `EmployeeBean`-ben a `@Named` annotáció helyett a `@ApplicationScoped` kellett használni
* `EmployeeRepository` átírása `PanacheRepository`-ra

Fejlesztés:

```
mvn quarkus:dev
```

## Natív fordítás

* Először fel kell tenni a GraalVM-et a https://github.com/graalvm/graalvm-ce-builds/releases címről
 a `graalvm-ce-java11-windows-amd64-20.1.0.zip` fájlt kell kitömöríteni
* Path

```
set GRAALVM_HOME=C:\Java\graalvm-ce-java11-20.1.0
set JAVA_HOME=C:\Java\graalvm-ce-java11-20.1.0
set PATH=%JAVA_HOME%\bin;%PATH%
```

* native-image telepítése:

```
gu install native-image
``` 

* Windowson telepítendő a [Visual Studio 2017 Visual C++ Build Tools](https://aka.ms/vs/15/release/vs_buildtools.exe), mely
több giga
* Majd létre kellett hozni egy `build.bat`-ot, melynek tartalma:

```
call "C:\Program Files (x86)\Microsoft Visual Studio\2017\BuildTools\VC\Auxiliary\Build\vcvars64.bat"
mvn package -Pnative
```

Ezzel buildelhető az alkalmazás, és létrejön egy exe.
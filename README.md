mvn deploy:deploy-file "-DpomFile=C:\Users\BulavkinSM\.m2\repository\ru\kontur\diadoc\diadocsdk\1.36.2.2-dev\diadocsdk-1.36.2.2-dev.pom"   "-Dfile=C:\Users\BulavkinSM\projects\diadocsdk-java-sfera\target\diadocsdk-1.36.2.2-dev.jar"   "-DrepositoryId=bcs-main-releases"   "-Durl=http://artifactory.gitlab.bcs.ru/artifactory/bcs-main-releases"


|              | Build Status
|--------------|--------------
| master       | [![Build status (master)](https://ci.appveyor.com/api/projects/status/2m2fh6avlbaq6ydf/branch/master?svg=true)](https://ci.appveyor.com/project/diadoc-admin/diadocsdk-java/branch/master)
| latest       | [![Build status (lastest)](https://ci.appveyor.com/api/projects/status/2m2fh6avlbaq6ydf?svg=true)](https://ci.appveyor.com/project/diadoc-admin/diadocsdk-java)


# diadocsdk-java

diadocsdk-java является официальной Java-реализацией клиента, использующего [публичный API Диадока](http://api-docs.diadoc.ru/).
На данный момент поддерживаются только JRE/JDK, на который установлен [КриптоПро JCP](https://www.cryptopro.ru/products/csp/jcp). Без КриптоПро JCP Diadoc SDK for Java работать не будет!


## Как использовать?

Вы можете [скачать готовый jar-файл diadocsdk-java со страницы релизов](https://github.com/diadoc/diadocsdk-java/releases).

Его можно [установить в локальный репозиторий maven](https://maven.apache.org/guides/mini/guide-3rd-party-jars-local.html) и начать использовать как зависимость:

    <dependencies>
      <dependency>
        <groupId>ru.kontur.diadoc</groupId>
        <artifactId>diadocsdk</artifactId>
        <version>1.36.2</version>
      </dependency>
    </dependencies>

## Сборка проекта с помощью maven

Для сборки проекта используется [maven](http://maven.apache.org/). Исполняемые файлы maven можно скачать [на официальном сайте](http://maven.apache.org/download.cgi) и установить [по инструкции](http://maven.apache.org/install.html). В качестве альтернативы, можно установить maven с помощью [Chocolatey](https://chocolatey.org/packages/maven). В итоге maven должен находиться в переменной среды PATH, чтобы его можно было вызвать из командной строки.

Стандартный способ сборки проекта с помощью maven (старт из корня репозитория):

```
mvn package
```

Можно поместить собранный пакет в локальный репозиторий командой:

```
mvn install
```

## Окончательная сборка проекта (CI)

Для окончательной сборки проекта используется утилита [Cake](http://cakebuild.net/).

Запуск powershell-скрипта `build.ps1` скачает утилиту Cake, если ее у вас нет, и запустит сборку проекта.
Из командной строки этот скрипт можно запустить с помощью `generate.bat`.

Выполняется:

- генерация версии на основе тега
- компиляция proto-файлов
- компиляция DiadocApi

## Добавление функциональности

- [Сделайте Fork](https://guides.github.com/activities/forking/)
- Создайте ветку для новой фичи (git checkout -b my-new-feature)
- Сделайте Commit изменений (git commit -am 'Add some feature')
- Сделайте Push новой ветки (git push origin my-new-feature)
- Создайте новый Pull Request

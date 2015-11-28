# kotlin-database

<!--[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-RxParse-brightgreen.svg?style=flat)](http://android-arsenal.com/details/1/1670)-->
<!--[![Download](https://api.bintray.com/packages/yongjhih/maven/kotlin-database/images/download.svg) ](https://bintray.com/yongjhih/maven/kotlin-database/_latestVersion)-->
[![JitPack](https://img.shields.io/github/tag/yongjhih/kotlin-database.svg?label=JitPack)](https://jitpack.io/#yongjhih/kotlin-database)
[![javadoc](https://img.shields.io/github/tag/yongjhih/kotlin-database.svg?label=javadoc)](https://jitpack.io/com/github/yongjhih/kotlin-database/-SNAPSHOT/javadoc/)
[![Build Status](https://travis-ci.org/yongjhih/kotlin-database.svg)](https://travis-ci.org/yongjhih/kotlin-database)
[![Join the chat at https://gitter.im/yongjhih/kotlin-database](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/yongjhih/kotlin-database?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

![](art/kotlin-database.png)

## Usage

Before:

```java
db.beginTransaction();
try {
  db.delete("users", "first_name = ?", new String[] { "Andrew" });
  db.setTransactionSuccessful();
} finally {
  db.endTransaction()
}
```

or

```java
Databases.from(db).inTransaction(it -> {
  it.delete("users", "first_name = ?", new String[] { "Andrew" });
});
```

After:

```kotlin
db.inTransation {
  delete("users", "first_name = ?", arrayOf("Andrew"))
}
```

## Installation

jcenter:

```gradle
dependencies {
    compile 'com.infstory:kotlin-database:1.0.0'
}
```

jitpack:

```gradle
repositories {
    // ...
    maven { url "https://jitpack.io" }
}
dependencies {
    compile 'com.github.yongjhih:kotlin-database:-SNAPSHOT'
}
```

## License

```
Copyright 2015 8tory, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

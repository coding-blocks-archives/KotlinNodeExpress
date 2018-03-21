
## REQUIREMENTS

1. NodeJS + NPM
2. Java (JVM + JRE) 1.8
3. Gradle
4. Kotlin + Kotlinc


## STEPS

### 1. Init Node

```
npm init
npm install kotlin
npm install express
```

### 2. Init Kotlin

New Gradle Kotlin DSL Build Script

```groovy
group = "com.codingblocks"
version = "0.1.0"

buildscript {
    ext.kotlin_version = '1.2.30'
    repositories {
        mavenCentral()
    }
    dependencies {
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
    }
}

apply plugin: 'kotlin2js'

repositories {
    mavenCentral()
}

dependencies {
    compile "org.jetbrains.kotlin:kotlin-stdlib-js:$kotlin_version"
}

compileKotlin2Js.kotlinOptions {
    moduleKind = "commonjs"
    outputFile = "dist/kotlib.js"
}
```

### 3. Directories

`dist`

`src/main/kotlin`


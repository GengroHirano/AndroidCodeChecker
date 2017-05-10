# AndroidCodeChecker
Androidのコードをチェックするやつ

#### Usage

* add `config` dir to project root.

* add `lint.xml` to app module.

* add code_checker.gradle to app module.

* insert code for app module.
```
apply from: file('code_checker.gradle')
```

* add lint options for app module.
```
lintOptions {
        disable 'InvalidPackage'
        abortOnError false

        xmlReport true
        xmlOutput new File("$project.buildDir/reports/lint/lint_results.xml")

        htmlReport true
        htmlOutput new File("$project.buildDir/reports/lint/lint_results.html")

        lintConfig file("lint.xml")
}
```

* start check task
```
./gradlew check
```



I made it as a reference
https://github.com/monstar-lab/gradle-android-ci-check

[![Build Status](https://travis-ci.org/mobidevke/CodeBuildShipKe.svg?branch=master)](https://travis-ci.org/mobidevke/CodeBuildShipKe)

# CodeBuildShipKe

##### Codelab demo

## Steps

### 1. Apk splitting
Why?
Smaller is always better :)
```
splits {
        abi {
            enable gradle.startParameter.taskNames.contains(":app:assembleRelease") || gradle.startParameter.taskNames.contains("assembleRelease")
            reset()
            include 'x86', 'x86_64', 'armeabi-v7a', 'arm64-v8a'
            universalApk true
        }
    }
```

### 2. Testing
Why? Who likes surprises??

Both instrumented and unit tests should present to ensure code quality

Add test coverage if you want (jacoco)


### 3. Code quality checks
- [Findbugs](https://gist.github.com/anonymous/3d0f7ef81cb1f10888716107b15bd146#file-findbugs-gradle)
- [AndroidLint](https://gist.github.com/anonymous/91a37be32ef97c7784fece6ffcf818a3#file-lint-gradle)
- [Checkstyle](https://gist.github.com/anonymous/f341928f752f816877d3870169b38c91#file-checkstyle-gradle)
- [PMD](https://gist.github.com/ianrumac/35fb89dd60e7a4c729f009b8412bf691#file-pmd-gradle)
- Ktlint (Kotlin)
- Detekt (Kotlin)

### 4. Deployment
There are many options, but the easiest option to work with is fastlane

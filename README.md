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
- Findbugs
- AndroidLint
- Checkstyle
- Ktlint (Kotlin)
- Detekt (Kotlin)

### 4. Deployment
There are many options, but the easiest option to work with is fastlane
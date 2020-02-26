pipeline {
  agent any
  stages {
    stage('Build APK') {
      steps {
        sh './gradlew :app:assembleDebug'
        sh './gradlew :app:assembleDebugAndroidTest'
      }
    }

    stage('Test APK') {
      steps {
        sh 'gcloud firebase test android run --app app/build/intermediates/apk_for_local_test/debugUnitTest/packageDebugUnitTestForUnitTest/apk-for-local-test.apk --test /app/build/intermediates/apk_for_local_test/debugUnitTest/packageDebugUnitTestForUnitTest/apk-for-local-test.apk'
      }
    }

  }
}
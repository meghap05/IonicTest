pipeline {
   agent any
      environment {
         PATH='/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:ANDROID_HOME=/Users/mp1244/Library/Android/sdk:Users/mp1244/Library/Android/sdk/build-tools:Users/mp1244/Library/Android/sdk/platform-tools:Users/mp1244/Library/Android/sdk/tools:/Applications/Android Studio.app/Contents/gradle/gradle-5.1.1/bin:/Applications/Android Studio.app/Contents/gradle/gradle-5.1.1/:/tools:/platform-tools:/Users/mp1244/Library/Android/sdk/tools:/Users/mp1244/Library/Android/sdk/platform-tools'
      }
   stages {
      stage('NPM Setup') {
      steps {
         sh 'npm install'
      }
   }

// stage('Platform add Android') {
//    steps {
//       sh 'if () ionic cordova platform add android@6.4.0'
//      } 
//   }

//   stage('Platform add iOS') {
//    steps {
//       sh 'ionic cordova platform add ios'
//      } 
//   }

  stage('Android Build') {
   steps {
      sh 'ionic cordova build android --release'
   }
  }

   stage('IOS Build') {
   steps {
      sh 'ionic cordova build ios --release'
     } 
  } 

   stage('APK Sign') {
   steps {
    //   sh 'jarsigner -storepass your_password -keystore keys/yourkey.keystore platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk nameApp'
    echo 'Signing APK'
   }
   }

   stage('Stage Web Build') {
      steps {
        sh 'npm run build --prod'
    }
  }

//    stage('Publish Firebase Web') {
//       steps {
//       sh 'firebase deploy --token "Your Token Key"'
//    }
//   }

   stage('Publish iOS') {
      steps {
       echo "Publish iOS Action"
    }
   }

   stage('Publish Android') {
     steps {
    echo "Publish Android API Action"
   }
  }

 }
}
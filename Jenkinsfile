node ('master'){
  stage('checkout ') {
    git 'https://github.com/executeautomation/SeleniumWithCucucumber.git'
  }

  stage('clean'){
     sh 'mvn clean'
  }
  stage('build & test') {
      sh 'mvn verify'
  }

  stage('report') {
 cucumber '**/*.json'
  }
  stage('Email'){
      emailext body: '''Completed Build.
      Checkout + Build + test + reporting.''', subject: 'Completed Jenkins build', to: 'gofokere@gmail.com'
  }
}

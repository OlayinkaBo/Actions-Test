# This workflow will build a Java project with Gradle
# For more information see: https://help.github.com/actions/language-and-framework-guides/building-and-testing-java-with-gradle

name: Java CI with Gradle

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

   jobs:
     build:
       runs-on: ubuntu-latest
       permissions:
         contents: read

       steps:
       - uses: actions/checkout@v4
       - name: Set up JDK 17
         uses: actions/setup-java@v4
         with:
           java-version: '17'
           distribution: 'temurin'

       - name: Set Gradle Wrapper permissions
         run: chmod +x ./gradlew

       - name: Build with Gradle Wrapper
         run: ./gradlew build
         # Actions-Test
# Actions-Test

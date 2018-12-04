Steps perform in app:

	1. Create library using bintray:

		Change in app build.gradle 
			1. Add app version details.
			ext {
				libVersionCode = 1
				libVersionName = '1.0.0'
				compileSdkVersion = 27
				targetSdkVersion = 27
				minSdkVersion = 15
				minSdkVersion = 15
				appVersion = 15
				appVersionName = '1.0'
			}
			2. Connect with bintray.
			 classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.7.3'
			 classpath 'com.github.dcendents:android-maven-gradle-plugin:2.0'
			 
			 
		Change in app build.gradle module
			1.  implementation project(':netbeacon') // library name
	
		Changes in library build.gradle

			ext {
				bintrayRepo = 'netbe' // your repo name for bintray u created
				bintrayName = 'netbe' // has to be same as your pakage name on bintray
				publishedGroupId = 'com.example.netbeacon' // your module package name
				libraryName = '/netbe'
				artifact = 'netbe'
				siteUrl = 'https://github.com/nishagcell/maven.netbe'
				gitUrl = 'https://github.com/nishagcell/maven.netbe'
				libraryVersion = '1.0'
				developerId = 'ngupta'
				developerName = 'Nisha'
				developerEmail = 'nisha@graycelltech.com'
				licenseName = 'The Apache Software License, Version 2.0'
				licenseUrl = 'http://www.apache.org/licenses/LICENSE-2.0.txt'
				allLicenses = ["Apache-2.0"]
				libraryDescription = 'A set of methods used to manipulate time object'

			}
			apply from: 'https://raw.githubusercontent.com/numetriclabz/jcenter/master/installv.gradle'
			apply from: 'https://raw.githubusercontent.com/numetriclabz/jcenter/master/bintrayv.gradle'

		Execute command in terminal:
			gradlew clean build install bintrayUpload

		local.properties
			bintray.user= “YOUR USERNAME”
			bintray.apikey= “YOUR API KEY”
			
	2. Steps perform in bintray account:
		1. Add repository
		2. Add package
		3. Also add below fields before sending add to jcentre request.
			Website
			https://github.com/nishagcell/sdktest
			Issue Tracker
			https://github.com/nishagcell/sdktest
			VCS
			https://github.com/nishagcell/sdktest
			
	3. Add local code to git repo
		https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/
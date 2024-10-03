# Fastlane iOS Deployment for Flutter App
This project demonstrates how to set up and automate iOS app deployment for a Flutter project using Fastlane and Firebase App Distribution.

## Prerequisites
1. Homebrew
Ensure you have Homebrew installed on your machine.

1. Flutter
Install Flutter by following the instructions here.

## Setting Up Fastlane
1. To install Fastlane using Homebrew, run the following command in your terminal:

```bash
brew install fastlane
```
2. Set up Match for Ad-Hoc Distribution
   
Fastlane Match allows you to manage iOS certificates and provisioning profiles across teams using a Git repository. You will need the following information:

* Git URL of the match repo
* Apple ID used for authentication
  
Run the following command to set up match for ad-hoc distribution:

```bash
fastlane match adhoc
```
You will be prompted to provide the Git URL and the Apple ID. Follow the on-screen instructions to complete the setup.

## Setting Up Firebase for App Distribution
1. To install the Firebase CLI globally, run:

```bash
npm install -g firebase-tools
```
2. Authenticate Firebase using the following command:

```bash
firebase login:ci
```
This will generate a Firebase token, which is needed for local deployments. You can store this token in an environment variable called $FIREBASE_TOKEN:

```bash
export FIREBASE_TOKEN=<your_token_here>
```

## Configuring Fastlane for Firebase App Distribution
1. Run the following command to add the Firebase App Distribution plugin to your Fastlane setup:

```bash
fastlane add_plugin firebase_app_distribution
```
2. Distribute the iOS App
Once everything is set up, you can deploy your app directly to Firebase App Distribution by running:

```bash
fastlane distribute_ios
```
## Conclusion

You now have a Fastlane setup for distributing your iOS app via Firebase App Distribution. The steps can be automated further through CI/CD pipelines like GitHub Actions. For more details on how to integrate with CI/CD, refer to the relevant sections of this project’s documentation.

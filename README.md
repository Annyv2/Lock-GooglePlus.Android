# Lock-GooglePlus

[![Build Status](https://travis-ci.org/auth0/Lock-GooglePlus.Android.svg?branch=master)](https://travis-ci.org/auth0/Lock-GooglePlus.Android)
[![License](http://img.shields.io/:license-mit-blue.svg?style=flat)](http://doge.mit-license.org)
[![Maven Central](https://img.shields.io/maven-central/v/com.auth0.android/lock-googleplus.svg)](http://search.maven.org/#browse%7C-2009911249)
[ ![Download](https://api.bintray.com/packages/auth0/lock-android/lock-googleplus/images/download.svg) ](https://bintray.com/auth0/lock-android/lock-googleplus/_latestVersion)

[Auth0](https://auth0.com) is an authentication broker that supports social identity providers as well as enterprise identity providers such as Active Directory, LDAP, Google Apps and Salesforce.

Lock-GooglePlus helps you integrate native Login with [Google+ Android SDK](https://developers.google.com/+/mobile/android/) and [Lock](https://auth0.com/lock)

## Requierements

Android 4.0 or later & Google Play Services 8.+

## Before you start using Lock-Google

In order to use Google APIs you'll need to register your Android application in [Google Developer Console](https://console.developers.google.com/project) and get your clientId.
We recommend follwing Google's [quickstart](https://developers.google.com/mobile/add?platform=android), just pick `Google Sign-In`. Then with your OAuth Mobile clientID from Google, the only step missing is to configure your Google Connection in [Auth0 Dashboard](https://manage.auth0.com/#/connections/social) with your recenlty created Google clientId.


> For more information please check Google's [documentation](https://developers.google.com/identity/sign-in/android/)

### Auth0 Connection with multiple Google clientIDs (Web & Mobile)

If you also have a Web Application, and a Google clientID & secret for it configured in Auth0, you need to whitelist the Google clientID of your mobile application in your Auth0 connection. With your Mobile clientID from Google, go to [Social Connections](https://manage.auth0.com/#/connections/social), select **Google** and add the clientID to the field named `Allowed Mobile Client IDs`

## Install

The Lock-GooglePlus is available through [Maven Central](http://search.maven.org) and [JCenter](https://bintray.com/bintray/jcenter). To install it, simply add the following line to your `build.gradle`:

```gradle
compile 'com.auth0.android:lock-googleplus:2.3.+'
```

Then in your project's `AndroidManifest.xml` add the following entries:

```xml
<uses-permission android:name="android.permission.GET_ACCOUNTS" />
<uses-permission android:name="android.permission.USE_CREDENTIALS" />
<meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />
```

## Usage

Just create a new instance of `GooglePlusIdentityProvider`

```java
GooglePlusIdentityProvider googleplus = new GooglePlusIdentityProvider();
```

and register it with your instance of `Lock`

```java
Lock lock = ...;
lock.setProvider(Strategies.GooglePlus.getName(), googleplus);
```

## Issue Reporting

If you have found a bug or if you have a feature request, please report them at this repository issues section. Please do not report security vulnerabilities on the public GitHub issue tracker. The [Responsible Disclosure Program](https://auth0.com/whitehat) details the procedure for disclosing security issues.

## What is Auth0?

Auth0 helps you to:

* Add authentication with [multiple authentication sources](https://docs.auth0.com/identityproviders), either social like **Google, Facebook, Microsoft Account, LinkedIn, GitHub, Twitter, Box, Salesforce, amont others**, or enterprise identity systems like **Windows Azure AD, Google Apps, Active Directory, ADFS or any SAML Identity Provider**.
* Add authentication through more traditional **[username/password databases](https://docs.auth0.com/mysql-connection-tutorial)**.
* Add support for **[linking different user accounts](https://docs.auth0.com/link-accounts)** with the same user.
* Support for generating signed [Json Web Tokens](https://docs.auth0.com/jwt) to call your APIs and **flow the user identity** securely.
* Analytics of how, when and where users are logging in.
* Pull data from other sources and add it to the user profile, through [JavaScript rules](https://docs.auth0.com/rules).

## Create a free account in Auth0

1. Go to [Auth0](https://auth0.com) and click Sign Up.
2. Use Google, GitHub or Microsoft Account to login.

## Author

Auth0

## License

Lock-Facebook is available under the MIT license. See the [LICENSE file](LICENSE) for more info.

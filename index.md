# How to Protect Your Digital Assets

### <https://protect-yourself.io/>

This is a practical guide on how to protect yourself and your digital assets, including (but not limited to):

 * Secure communication (such as **voice calls** and **messaging**)
 * Protecting online accounts (**Google**, **Facebook**, **Twitter**)
 * Protecting personal data (documents, financial accounts)
 * Protecting mobile phones
 * Protecting personal computers

This guide is intentionally prescriptive and action. There may be endorsement certain products, but it is not necessarily comprehensive. In certain cases, there may be alternative methods or products which are more suitable for your needs. This is not a panacea for all your personal security problems, but rather a good starting point for anyone concerned about their personal digital privacy and security.

If you'd like to make a contribution, have questions, or want to leave feedback, [please do so through GitHub](https://github.com/brndnmtthws/protect-yourself).

## How to Read This Guide

It's recommended you begin by familiarizing yourself with the [core concepts](#core-concepts), and then moving on to the relevant [actionable topics](#action). You should focus on the following priorities:

1. Secure access to your mobile phones
2. Secure access to your PCs
3. Secure online account access
4. Safe browsing
5. Secure cloud storage

# Core Concepts

### Password Management

Passwords should be managed using a _password manager_. A password manager is a tool that stores passwords securely, and usually provides other useful features such as syncing across devices, backups, mobile apps, and more. Rather than remembering a password for each individual website or service you use, you should create very strong password to unlock your password manager, and then generate a new random password for each individual website or service that you use. You never need to memorize these passwords.

This has some important advantages over memorizing passwords, such as:

* If your password for a particular website or service becomes compromised, it will not affect other websites or services (since each password is unique)
* By not knowing your passwords, you are less likely to accidentally share your password
* Password managers includes tools for notifying you when a password may have been compromised, so you can change it

#### Open Source Password Managers:

* [KeePass](http://keepass.info/)
* [KeePassX](https://www.keepassx.org/)
* [Bitwarden](https://bitwarden.com)
     * Subscription with additional options available
     * Base features of password management are free

#### Commercial Source Password Managers:

* [1Password](https://1password.com/)
* [LastPass](https://www.lastpass.com/)
* [Dashlane](https://www.dashlane.com/)

### 2-factor Authentication (2FA)

[2-factor authentication](https://en.wikipedia.org/wiki/Multi-factor_authentication) (referred to as _2FA_) is a method of securely identifying yourself, whereby you use 2 pieces of secure information to prove you are who you are. In practice, you combine _something you know_ with _something you have_. For example, you could combine a password with a special code (or one-time password) which is generated using a mathematical formula. This code may be provided by receiving an SMS message, a phone call, an email, or using a OTP app like [Google Authenticator](https://en.wikipedia.org/wiki/Google_Authenticator).

[2FA is widely supported](https://twofactorauth.org/), but not yet implemented by all online services. If a service you use doesn't support it, you should petition them to add 2FA support. Furthermore, you may want to consider whether or not a service properly supports 2FA before using their products. For example, you may want to choose a bank based on whether or not they support 2FA.

In this guide, it's recommended that you use a [hardware authentication device](https://en.wikipedia.org/wiki/Security_token#Physical_types) for 2FA. Specifically, you should consider using a [YubiKey](https://www.yubico.com/products/) or a similar device. The YubiKey will be referenced elsewhere in this document. Telephony based 2FA, including SMS and voice calls, is **considered insecure and should be avoided**. In order of preference, it's recommended that you use:

1. [Hardware Security Tokens](https://en.wikipedia.org/wiki/Security_token) - **Most secure overall**
     * A piece of hardware that can be linked to several different types of 2FA standards
     * Standards:
          * [CTAP1/CTAP2/U2F/UAF/FIDO2/WebAuthN](https://en.wikipedia.org/wiki/FIDO_Alliance)
               * Most secure form of hardware token
               * Far less services that support
          * [YubiOTP](https://www.yubico.com/resources/glossary/yubico-otp/)
               * Somewhat more secure than normal OTP
               * Likely even less support than FIDO standards
               * Proprietary to Yubico/Yubikey
          * [OTP](https://en.wikipedia.org/wiki/One-time_password)[/HOTP/TOTP/OCRA](https://en.wikipedia.org/wiki/Initiative_for_Open_Authentication)[/OAUTH](https://en.wikipedia.org/wiki/FIDO_Alliance)
               * Least secure form of hardware token
               * More common for services to support as a 2FA option
               * Hardware token can take the place of any software based 2FA app
     * Devices:
          * [YubiKey](https://www.yubico.com/products/yubikey-hardware/yubikey4/)
               * While FIDO and CTAP standards are hardware agnostic, Yubikey is often synonymous with hardware tokens or the number one go to solution
               * Compatible with many interfaces including USBC/USBA/NFC and more
               * Fingerprint support
               * Range of models to support various needs
          * [Thetis](https://thetis.io)
               * Bluetooth support
               * Fingerprint support
          * [Google Titan](https://cloud.google.com/titan-security-key/)
               * USBA/USBC/NFC support
               * Older models had known vulnerabilities
2. [Software-based OTP Tool](https://en.wikipedia.org/wiki/Software_token) - **Less secure**
     * Typically an app on a device that contains regenerating codes
     * Apps:
          * [Bitwarden](https://bitwarden.com)
               * Also a password manager allowing for a single pane of glass for password and OTP management
               * Supports FIDO2/WebAuthN/U2F/UAF/CTAP1/CTAP2 hardware tokens as a 2FA login option
               * Also has capabilities to store and send secure notes, store and send secure files, and share credentials with others
               * Works on phones, computers, and has browser plugin
               * OTP and hardware tokens usage requires a $10 a year subscription
               * Open source
               * Host yourself or with Bitwarden
          * [Google Authenticator](https://en.wikipedia.org/wiki/Google_Authenticator)
               * OTP and push notification support
               * Only works on phones
          * [Authy](https://www.authy.com/)
               * Tied to your phone number and nothing else
               * Works on phone and computer
3. Trusted email account to receive OTP (preferably one which requires 2FA) - **Less secure**
     * If your email is comprimised then presumably any accounts you have attached to it could be comprimised
     * Consider an email service that focuses on privacy and security such as:
          * [Protonmail](https://www.protonmail.com)
          * [Tutanota](https://tutanota.com)
          * [Lavabit](https://lavabit.com)
4. SMS or voice call to receive OTP - **Least secure**
     * OTP that is done over a phone call or text message
     * Easier to phish
     * Many services will offer SMS or voice calls as an account recovery method in case you cannot login
     * **Phone-based recovery methods (SMS & voice) should be disabled, if possible**

### Encryption

[Encryption](https://en.wikipedia.org/wiki/Encryption), when applied to your data, is a method of making it difficult for unauthorized parties to intercept data and know what you've written, said, where you've been, or what you've done. It does not guarantee that others can't intercept or read your data, but it can make it extremely difficult, _if applied correctly_. For example, you may want to encrypt your text messages or phone calls so nobody can snoop on them.

Many services advertise and include encryption, but very few of them are actually secure because they typically store the _private keys_ as part of the service. This means that if that service itself becomes compromised, your data may not be safe. Most internet-based services operate this way.

This guide will discuss some options for safely encrypting data for certain applications, but there are far too many tools, services, and applications to discuss each one. There is a section on [using GnuPG](gnupg.html), a powerful encryption tool, and a kind of Swiss army knife for privacy.

# Action

* [How to Secure Access to Your Mobile Devices](secure-mobile.html)
  * [Android](secure-mobile.html#android)
  * [iOS](secure-mobile.html#ios)
* [How to Secure Access to Your PC](secure-pc.html)
  * [macOS](secure-pc.html#macos)
  * [Linux](secure-pc.html#linux)
  * [Windows](secure-pc.html#windows)
* [How to Communicate Securely](secure-communication.html)
  * [Phone & SMS](secure-communication.html#phone--sms)
  * [Messaging](secure-communication.html#messaging)
  * [Email](secure-communication.html#email)
* [How to Secure Your Online Accounts](secure-online-accounts.html)
  * [Google](secure-online-accounts.html#google)
  * [Facebook](secure-online-accounts.html#facebook)
  * [Twitter](secure-online-accounts.html#twitter)
* [How to Browse the Web Safely](safe-browsing.html)
  * [Google Chrome](safe-browsing.html#google-chrome)
  * [Firefox](safe-browsing.html#firefox)
  * [Safari](safe-browsing.html#safari)
* [How to Store Data Securely Online](secure-storage.html)
  * [SpiderOak](secure-storage.html#spideroak)
  * [Dropbox](secure-storage.html#dropbox)
  * [Google Drive](secure-storage.html#google-drive)
  * [Apple iCloud](secure-storage.html#apple-icloud)
  * [Box](secure-storage.html#box)
* [How to Use Your YubiKey with GnuPG](gnupg.html)
  * [File Encryption](gnupg.html#file-encryption)
  * [SSH Key Management](gnupg.html#ssh-key-management)

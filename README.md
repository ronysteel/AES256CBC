# AES256CBC

The **most convenient**, simple & lightweight **Swift 2** framework to encrypt / decrypt a string with **AES-256 CBC** encryption.

AES256CBC is meant as simple, stand-alone file to bring [AES-256](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) [Cipher Block Chaining](https://en.wikipedia.org/wiki/Block_cipher_mode_of_operation#Cipher_Block_Chaining_.28CBC.29) encryption to any Swift 2 powered app without any friction or learning curve. It is used in multiple projects of [SwiftyBeaver](https://github.com/SwiftyBeaver) and was developed in cooperation with Marcin Krzyżanowski from [CryptoSwift](https://github.com/krzyzanowskim/CryptoSwift).

## Unique Feature Set

1. Just **a single file** in pure Swift 2 source code
2. Runs **natively** on iOS, Mac OSX, tvOS & watchOS
3. No additional dependencies or header files
4. Maximum **convenience** for encrypting / decrypting of strings
5. Built-in generating of compatible 32 character password
6. Automatic string padding
6. Automatic handling & embedding of a **random initialisation vector**
   
Please **follow [SwiftyBeaver on Twitter](https://twitter.com/SwiftyBeaver)** to stay up-to-date on new versions.

## Requirements

- iOS 8.0+ / Mac OS X 10.9+
- Xcode 7

## Installation

#### Platform & Installation Support



| \                                        | iOS 8+             | OSX 10.9+          | watchOS 2+         | tvOS 9+            |
| ---------------------------------------- | ------------------ | ------------------ | ------------------ | ------------------ |
| [Swift Package Manager](https://swift.org/package-manager/) | <center>✅</center> | <center>✅</center> | <center>✅</center> | <center>✅</center> |
| [Carthage](https://github.com/Carthage/Carthage) | <center>✅</center> | <center>✅</center> | <center>✅</center> | <center>✅</center> |
| [CocoaPods](https://cocoapods.org)       | <center>✅</center> | <center>✅</center> | <center>✅</center> | <center>✅</center> |
| Download                                 | <center>✅</center> | <center>✅</center> | <center>✅</center> | <center>✅</center> |

For installation details please see the next points.

#### via Carthage

You can use [Carthage](https://github.com/Carthage/Carthage) to install AES256CBC by adding that to your Cartfile:

``` 
github "SwiftyBeaver/AES256CBC"
```

#### via CocoaPods

To use [CocoaPods](https://cocoapods.org) just add this to your Podfile:

``` 
pod 'AES256CBC'
```

#### via Swift Package Manager

To use AES256CBC as a [Swift Package Manager](https://swift.org/package-manager/) package just add the following in your Package.swift file.

``` Swift
import PackageDescription

let package = Package(
name: "HelloWorld",
dependencies: [
.Package(url: "https://github.com/SwiftyBeaver/AES256CBC.git", majorVersion: 0)
]
)
```

#### or Download

1. Download the latest release zip from [here](https://github.com/SwiftyBeaver/AES256CBC/releases)
2. Drag & drop the `/sources` folder into your project (make sure "Copy items if needed" is checked)
3. Rename the "sources" group to "AES256CBC" if you'd like

Note: You don't have to `import AES256CBC` if you install this way.


## Usage

Example which encrypts and decrypts a string using a randomly generated 32 character password. In real-life you would **add your own 32 character password** instead.

``` Swift
import AES256CBC

let str = "My little secret"
let password = AES256CBC.generatePassword()  // returns random 32 char string

// get AES-256 CBC encrypted string
let encrypted = AES256CBC.encryptString(str, password: password)

// decrypt AES-256 CBC encrypted string
let decrypted = AES256CBC.decryptString(encrypted!, password: password)
```

## FAQs

### Why do I get nil as result?
If anything goes wrong, most likely due to a password which is not 32 characters long, then `encryptString()` and `decryptString()` return nil.



### What about the initial vector?

You don’t need to worry about the important initial vector which is required to make AES-256 much more secure. AES256CBC automatically generates a random initial vector for you and adds it to the start of the encrypted string. During decryption AES256CBC reads the first 16 characters of the encrypted string and uses them as initial vector to decrypt the remaining encrypted string.


## Contact & Contribute

If you have questions please contact Sebastian via the dedicated [SwiftyBeaver Twitter account](https://twitter.com/SwiftyBeaver). Feature requests or bugs are better reported and discussed as Github Issue.

**Please contribute back** any great stuff, especially bugfixes & security issues! Each new bugfix, feature request or addition/change should be put in **a dedicated pull request** to simplify discussion and merging.

Thanks for testing, sharing, staring & contributing!


## License

AES256CBC is released under the [MIT License](https://github.com/SwiftyBeaver/AES256CBC/blob/master/LICENSE). The core crypto logic is a tailored version of [CryptoSwift](https://github.com/krzyzanowskim/CryptoSwift) written by Marcin Krzyżanowski, please read & respect his license which can be found in the middle of the file [AES256CBC.swift](https://github.com/SwiftyBeaver/AES256CBC/blob/master/sources/AES256CBC.swift), too.


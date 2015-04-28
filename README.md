# SigningFun

A master/detail app with a list of products on the master side. Each row in the table view of products shows the icon, the name, and the bundle ID. When a product is selected, the detail side should show a text field with the profile identifier and certificate name (file name) that should be used when building the app.

To keep this simple, the app is hardcoded to always look in “~/Desktop/SigningFun/“ to load the constituent pieces (You can add it in ~/Library/Application Support/ and configure accordingly).

Products
For the sake of simplicity, these are just “.product” folders with a plist called “Info.plist”. This bears no resemblance to actual Info plists, the name is just the same.

The info plist defines two keys: the name and the bundle ID.

The package also includes an Icon called “Icon”.

Certificates
These are just text files with a “.fakecertificate” extension. Treat them as opaque blobs of data (as in - there’s no value in trying to parse/understand the contents, it’s just garbage I made up and put in there). The file name is treated as the “name” of the certificate (i.e. iOS Developer Bar.fakecertificate has the name “iOS Developer Bar”)

Profiles
These are plists with a “.fakeprofile” extension (they are XML so you can easily inspect them). They have three keys:
• BundleID (the bundle ID of the app that this profile can be used with)
• Identifier (a UUID that identifies this profile)
• CertificateHash (the SHA1 hash of the certificate file that can be used with this profile)

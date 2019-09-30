SSL ERROR 133
A user recently reported this error message to me as he tried to use Cydia Impactor on his Mac and it shows:

http-sox.cpp:133 An SSL error has occurred and a secure connection to the server can not be made.

…after he entered his Apple ID credentials.

I didn’t personally experience this trouble, so the following fix was contributed by a user from Reddit.

Force close Cydia Impactor
Launch iTunes and sync your device
Quit iTunes and re-open Cydia Impactor
Try to sideload your app again.

HTTP-WIN.CPP:158
We just talked about an SSL error in Cydia Impactor, so mind as well mentions another one.

Peer certificate cannot be authenticated with given CA certificates. SSL certificate problem: self signed certificate in certificate chain

Cydia Impactor Errors: The Complete List & How to Fix Them 2

Lucky for you, this problem can be solved without having to do much. Saurik just updated his tool to address to issue. All you have to do is uninstall your current version and click here to download the latest update of Cydia Impactor.

ERROR 68
If you see a popup that says,

ios/addAppId

An invalid value ‘CY- mach_portal’ was provided for the parameter ‘appIdName

Then you might want to also upgrade your Cydia Impactor to the newest version.

INSTALLATION ERROR 42
Unlike other errors, this one actually gives you an explanation that’s easy to understand. If you didn’t catch it, I will repeat it again.

The system version is lower than the minimum OS version specified for bundle…

In other words, your iPhone or iPad isn’t running on one of the iOS version that’s compatible with the app. Best thing to do is upgrade your firmware.

Alternative fix if extra_recipe is refusing to install.

Unzip the IPA
Navigate to Payload > extra_recipe > Select show package contents > Payload > Info.plist
Change MinimumOSVersion to 10.0.0
Compress the Payload file
Change its extension from .ZIP to .IPA
Now try again using Cydia Impactor. Thanks /u/System0verlord

ERROR 179
Here’s the full log:

ipa.cpp 179 application already installed as incompatible team

If you encountered this problem while re-jailbreaking your home depot jailbreak or yalu, then the best thing to do is remove either app from your iOS device and then try again.

LOCKDOWN ERROR
Sounds a bit extreme isn’t it?

lockdown.cpp:57
LOCKDOWN_E_SSL_ERROR

Don’t worry; I had this issue before in Cydia Impactor. The way I troubleshoot this problem was super easy.

Disconnect your device from the computer. On your iPhone, go to Settings > General > Reset > Reset Location and Privacy. Plug your device back to the computer and open iTunes. On your iPhone screen, it should have a popup with the “Trust” button on it, tap on that and you can use Cydia Impactor again.

The lockdown:57 error will eventually go away.

Note: If you received this error while running iOS 11, it means that Cydia Impactor is not compatible with your firmware yet. To learn more about that, read this article.

ERROR 62
provision.cpp:62 _assert(reponse.head[“content-type”] == “text/x-xml-plist”)

The fix for this error is quite weird if you ask me. Just keep entering your Apple Id and password until the error no longer appear.

But many time? Several users reported that it took them about 5 – 10 tries until Impactor would start working again.

ERROR 71
Someone on Twitter recently reached out to me and asked about an error in Cydia Impactor called provision.cpp:71. Although upgrading to the latest version will not help you resolve this issue, we have found a way to fix it.

ios/SubmitDevelopmentCSR=7460

You already have a current iOS Development certificate or pending certificate request.

This one has been popping up a lot lately.

Cydia Impactor Errors: The Complete List & How to Fix Them 3

Here’s a quick excerpt from the detailed guide on how to fix it.

Launch Cydia Impactor on your Mac or Windows computer
Click Revoke Certificates under the Xcode menu
Enter your Apple ID
PLIST.HPP:92
./plist.hpp:92 _assert(plist_get_node_type(plist) == PLIST_STRING)

Technically this is an error, but it won’t prevent Impactor from installing the app on your device. In fact, once you see the hpp:92 warning, it means the app has been successfully installed.

Just open your iPhone and check if the application is there. In most cases, it should.

STUCK ON PREFLIGHTINGAPPLICATION
When you install an IPA through Cydia Impactor, it will show a progress bar to let you know the current installation status. At some point in time, you might be stuck at “PreflightingApplication”. This means your iOS device and the app you’re trying to sideload is incompatible with each other.

For example, you can’t install a Pangu jailbreak on a 32-bit device. To solve this issue, you will have to download the right IPA file.

STUCK ON VERIFYINGAPPLICATION
Cydia Impactor Errors: The Complete List & How to Fix Them 4
Image credit: /user/DeyyTeam

Unlike other errors, when Cydia Impactor is stuck at the VerifyingApplication screen, it means there’s a lost in connections between the utility, the IPA file, and your iOS device.

To fix this problem, use one of the following tips:

Turn on Airplane Mode and turn it off (after a minute or so)
Hard resetting your iPhone or iPad
Delete the existing profile from the Settings app (if this happen during a re-sign process)
Check for two-factor authentication
I was able to get past the VerifyingApplication log after deleting Yalu and rebooted my device.

PROVISION.CPP:138 MAXQUANTITY
Users have been seeing this new error called provision.cpp:138 which we were unable to find the cause behind it. As of now, we’ve tried the revoke certificate method, making a new Apple ID account, and using a different IPA source. Nothing has helped so far.

The best way to bypass this error at the moment is to install your IPA from a third-party app installer. You can check out a full list of them from here.

Update #1: Saurik just updated Cydia Impactor to version 0.9.44. According to the changelog, this update should fix the “maxQuantity error due to Apple change”.

# fastlane  
> ð The easiest way to automate building and releasing your iOS and Android apps

## Reference

- [fastlane](https://github.com/fastlane/fastlane)
- [Running a Custom Bash Script in fastlane](https://spin.atomicobject.com/2021/05/21/custom-bash-script-fastlane/)

## Extend

- [IPABuildShell](https://github.com/aa335418265/IPABuildShell) 
    > ä¸ä¸ªå¼ºå¤§çãè½»éç iOS èªå¨æåå·¥å·ï¼æ éæå¨æå®æææä»¶åè¯ä¹¦
- [AutoPacking-iOS](https://github.com/stackhou/AutoPacking-iOS) 
    > iOSèªå¨æåèæ¬ å¤é¡¹éæ© ä¸è¡ä¸ä¼ æå®ä½ç½®

## Commands

``` bash
$ brew cask install fastlane    # install fastlane

$ fastlane install_plugins  # install plugins
$ fastlane update_plugins   # update plugins
```

## Fastfile
> fastlane èªå¨åèæ¬æä»¶

## Appfile
> App ç¸å³ä¿¡æ¯

## Deliverfile
> App äº¤ä»æä»¶ï¼è®¾ç½®

## Pluginfile
> æä»¶éç½®æä»¶

## Solutions

- Cannot proceed with delivery: an existing transporter instance is currently uploading this package
    > [an existing transporter](https://stackoverflow.com/questions/3870082/application-loader-cannot-proceed-with-delivery-an-existing-transporter-insta)
    > 
    > Solution: `$ rm -rf ~/Library/Caches/com.apple.amp.itmstransporter/UploadTokens/`


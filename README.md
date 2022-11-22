# Package5923

This package provides a minimal, reproducible example of the issue reported in
https://github.com/apple/swift-package-manager/issues/5923.

To reproduce the issue:
1. Clone this package, and `cd` into it
2. Run `swift build`

The below logs show how the package failed to build.
```
‣ swift build
warning: Usage of /Users/nickcooke/Library/org.swift.swiftpm/collections.json has been deprecated. Please delete it and use the new /Users/nickcooke/Library/org.swift.swiftpm/configuration/collections.json instead.
[1/1] Planning build
Building for debugging...
While building module 'Foundation' imported from /Users/nickcooke/Developer/Package5923/.build/x86_64-apple-macosx/debug/Package5923.build/DerivedSources/resource_bundle_accessor.h:1:
In file included from <module-includes>:1:
In file included from /Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/Foundation.h:8:
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:523:1: error: expected identifier or '('
@class NSString, Protocol;
^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:525:9: error: unknown type name 'NSString'
typedef NSString * NSExceptionName NS_TYPED_EXTENSIBLE_ENUM;
        ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:526:9: error: unknown type name 'NSString'
typedef NSString * NSRunLoopMode NS_TYPED_EXTENSIBLE_ENUM;
        ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:528:19: error: unknown type name 'NSString'
FOUNDATION_EXPORT NSString *NSStringFromSelector(SEL aSelector);
                  ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:529:44: error: unknown type name 'NSString'
FOUNDATION_EXPORT SEL NSSelectorFromString(NSString *aSelectorName);
                                           ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:531:19: error: unknown type name 'NSString'
FOUNDATION_EXPORT NSString *NSStringFromClass(Class aClass);
                  ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:532:53: error: unknown type name 'NSString'
FOUNDATION_EXPORT Class _Nullable NSClassFromString(NSString *aClassName);
                                                    ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:534:19: error: unknown type name 'NSString'
FOUNDATION_EXPORT NSString *NSStringFromProtocol(Protocol *proto) API_AVAILABLE(macos(10.5), ios(2.0), watchos(2.0), tvos(9.0));
                  ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:534:50: error: missing '#include <objc/runtime.h>'; 'Protocol' must be declared before it is used
FOUNDATION_EXPORT NSString *NSStringFromProtocol(Protocol *proto) API_AVAILABLE(macos(10.5), ios(2.0), watchos(2.0), tvos(9.0));
                                                 ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/usr/include/objc/runtime.h:60:28: note: declaration here is not visible
typedef struct objc_object Protocol;
                           ^
While building module 'Foundation' imported from /Users/nickcooke/Developer/Package5923/.build/x86_64-apple-macosx/debug/Package5923.build/DerivedSources/resource_bundle_accessor.h:1:
In file included from <module-includes>:1:
In file included from /Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/Foundation.h:8:
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:535:61: error: unknown type name 'NSString'
FOUNDATION_EXPORT Protocol * _Nullable NSProtocolFromString(NSString *namestr) API_AVAILABLE(macos(10.5), ios(2.0), watchos(2.0), tvos(9.0));
                                                            ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:539:30: error: unknown type name 'NSString'
FOUNDATION_EXPORT void NSLog(NSString *format, ...) NS_FORMAT_FUNCTION(1,2) NS_NO_TAIL_CALL;
                             ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:539:53: error: format argument not an NSString
FOUNDATION_EXPORT void NSLog(NSString *format, ...) NS_FORMAT_FUNCTION(1,2) NS_NO_TAIL_CALL;
                             ~~~~~~~~~~~~~~~~       ^                  ~
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:94:49: note: expanded from macro 'NS_FORMAT_FUNCTION'
        #define NS_FORMAT_FUNCTION(F,A) __attribute__((format(__NSString__, F, A)))
                                                       ^                    ~
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:540:31: error: unknown type name 'NSString'
FOUNDATION_EXPORT void NSLogv(NSString *format, va_list args) NS_FORMAT_FUNCTION(1,0) NS_NO_TAIL_CALL;
                              ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:540:63: error: format argument not an NSString
FOUNDATION_EXPORT void NSLogv(NSString *format, va_list args) NS_FORMAT_FUNCTION(1,0) NS_NO_TAIL_CALL;
                              ~~~~~~~~~~~~~~~~                ^                  ~
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObjCRuntime.h:94:49: note: expanded from macro 'NS_FORMAT_FUNCTION'
        #define NS_FORMAT_FUNCTION(F,A) __attribute__((format(__NSString__, F, A)))
                                                       ^                    ~
While building module 'Foundation' imported from /Users/nickcooke/Developer/Package5923/.build/x86_64-apple-macosx/debug/Package5923.build/DerivedSources/resource_bundle_accessor.h:1:
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/usr/include/objc/module.modulemap:8:10: error: module 'ObjectiveC.NSObject' requires feature 'objc'
  module NSObject {
         ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObject.h:6:9: note: submodule of top-level module 'ObjectiveC' implicitly imported here
#import <objc/NSObject.h>
        ^
While building module 'Foundation' imported from /Users/nickcooke/Developer/Package5923/.build/x86_64-apple-macosx/debug/Package5923.build/DerivedSources/resource_bundle_accessor.h:1:
In file included from <module-includes>:1:
In file included from /Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/Foundation.h:10:
In file included from /Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSArray.h:5:
In file included from /Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObject.h:8:
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSZone.h:9:1: error: expected identifier or '('
@class NSString;
^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSZone.h:19:63: error: unknown type name 'NSString'
FOUNDATION_EXPORT void NSSetZoneName(NSZone * _Nullable zone, NSString *name)NS_SWIFT_UNAVAILABLE("Zone-based memory management is unavailable");
                                                              ^
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSZone.h:20:19: error: unknown type name 'NSString'
FOUNDATION_EXPORT NSString *NSZoneName(NSZone * _Nullable zone) NS_SWIFT_UNAVAILABLE("Zone-based memory management is unavailable");
                  ^
While building module 'Foundation' imported from /Users/nickcooke/Developer/Package5923/.build/x86_64-apple-macosx/debug/Package5923.build/DerivedSources/resource_bundle_accessor.h:1:
In file included from <module-includes>:1:
In file included from /Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/Foundation.h:10:
In file included from /Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSArray.h:5:
/Applications/Xcode_13.3.1.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX12.3.sdk/System/Library/Frameworks/Foundation.framework/Headers/NSObject.h:10:1: error: expected identifier or '('
@class NSInvocation, NSMethodSignature, NSCoder, NSString, NSEnumerator;
^
fatal error: too many errors emitted, stopping now [-ferror-limit=]
In file included from <built-in>:1:
/Users/nickcooke/Developer/Package5923/.build/x86_64-apple-macosx/debug/Package5923.build/DerivedSources/resource_bundle_accessor.h:1:9: fatal error: could not build module 'Foundation'
#import <Foundation/Foundation.h>
 ~~~~~~~^
21 errors generated.
[0/1] Compiling Package5923 foo.c
```

# RNIOSDemo

A React Native iOS simulator demo app with CI/CD via GitHub Actions.

## Build

```bash
npm install
cd ios && pod install && cd ..
xcodebuild build \
  -workspace ios/RNIOSDemo.xcworkspace \
  -scheme RNIOSDemo \
  -sdk iphonesimulator \
  -configuration Debug \
  -derivedDataPath build \
  CODE_SIGN_IDENTITY="" \
  CODE_SIGNING_ALLOWED=NO
```

## CI/CD

The GitHub Actions workflow builds the iOS simulator app and uploads it to AutoDevice on every push to `main`.

### Required Secrets

- `AUTODEVICE_API_KEY` — API key for AutoDevice

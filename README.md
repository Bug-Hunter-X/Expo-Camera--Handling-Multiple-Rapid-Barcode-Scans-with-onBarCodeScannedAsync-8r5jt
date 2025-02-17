# Expo Camera: Handling Multiple Rapid Barcode Scans

This repository demonstrates a bug and its solution related to the Expo Camera API's `onBarCodeScannedAsync` function. When scanning barcodes rapidly, multiple scan events may be triggered in quick succession, leading to crashes or unexpected behavior if not handled correctly. The solution involves debouncing or throttling the event handling to prevent overwhelming the application.

## Bug Description

The core issue is the asynchronous nature of barcode scanning. If the camera rapidly scans multiple barcodes, `onBarCodeScannedAsync` might fire multiple times before the previous scan's data is processed, causing race conditions and potential application instability.

## Solution

The solution uses `lodash`'s `debounce` function to limit the rate at which the `onBarCodeScanned` function is called. This effectively throttles the incoming barcode scan events, ensuring the app can process each scan before receiving the next one. This avoids the issue of multiple events triggering at almost the same time, preventing the overwhelming of the application.

## Setup

1. Clone the repository
2. Navigate to the project directory.
3. Run `npm install` or `yarn install`.
4. Start the app using `expo start`.
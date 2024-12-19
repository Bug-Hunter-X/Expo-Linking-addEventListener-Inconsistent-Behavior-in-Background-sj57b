# Expo Linking.addEventListener Inconsistent Behavior in Background

This repository demonstrates an uncommon bug related to the Expo `Linking` API's `addEventListener`. When the app is in the background and a deep link is opened, the event listener sometimes fails to trigger, leading to missed actions.

## Bug Description:
The `Linking.addEventListener` method is not consistently firing when the app is already running in the background.  Deep links intended to trigger actions within the app are sometimes ignored, leading to unexpected behavior.

## How to Reproduce:
1. Clone this repository.
2. Run the app on an iOS or Android device.
3. Send a deep link to the app while it's running in the background.
4. Observe that the event listener may not always trigger, even though the deep link is valid.

## Solution:
The provided solution uses a combination of `Linking.getInitialURL` and a background task to reliably handle deep links.
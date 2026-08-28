# Privacy

This document describes the data handling of the current Training Wheels alpha.

## Information read locally

Training Wheels reads the following information on the user's computer:

- The visible League of Legends game window and its HUD pixels, for local screen capture and HUD mirroring.
- Local League Client gameflow information, read-only and only to determine whether the overlay is allowed to run for the current session.

The League Client information is used only for eligibility gating, such as whether a supported game mode is currently in progress. It is not used for gameplay analysis.

## Information not read or performed

Training Wheels does not:

- Read game-process memory
- Inject DLLs or modify the game client
- Send gameplay input or automate gameplay
- Collect an account password
- Persist Riot authentication information
- Persist League Client lockfile contents

## Local settings

Training Wheels stores the following settings locally in:

```text
%LOCALAPPDATA%\TrainingWheels\mirror-settings.json
```

The file may contain:

- Mirror group positions
- Category on/off choices
- Selected item slots
- Opacity
- Scale
- Capture mode preference

To remove these settings, close Training Wheels and delete the file above.

## Network and external transmission

The current alpha has no telemetry, analytics, cloud upload, or user-tracking implementation.

For local eligibility gating, it sends a read-only request to the locally running League Client. The required local connection details are used only in memory for that request and are not persisted or logged by Training Wheels.

Training Wheels does not upload HUD captures, settings, or League Client responses.

## Changes to this policy

If a future release adds data collection, external communication, or a cloud service, this policy will be updated before that release.

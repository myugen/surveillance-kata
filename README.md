# Surveillance System

Manual Mocks are okay, but sometimes we need some extra help from third party libraries. It’s important to understand when it is okay, and when we are coupling our test definitions to the third party’s. Attendees should be able to discern when they feel more comfortable with each option.

- **Estimated time:** 2 hours
- **Format:** Pairs

## The Problem

We want to create a Surveillance System that records video when something is moving. We have purchased two devices:

- A sensor that will be able to send a signal to our code when movement is detected, and another signal when movement stops.
- A video recorder that we can invoke via API to start and stop recording.

Test and implement the necessary code for making those components interact.

## Library Definition

```mermaid
classDiagram
    class SensorStatus {
        <<Enumeration>>
        START_DETECTION
        STOP_DETECTION
    }

    class SensorEvent {
        SensorStatus status
        Instant occurredAt
    }

    class SensorListerner {
        <<Interface>>
        onDetect(SensorEvent event) void
    }

    class Sensor {
        <<Interface>>
        subscribe(SensorListener listener) void
    }

    class Recorder {
        <<Interface>>
        startRecording() void
        stopRecording() void
    }

```

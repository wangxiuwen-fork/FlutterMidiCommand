# flutter_midi_command

A Flutter plugin for sending and receving MIDI messages between Flutter and physical and virtual MIDI devices. 

Wraps CoreMIDI and android.media.midi in a thin dart/flutter layer.
Works with USB and BLE MIDI connections on Android, and USB, network(session) and BLE MIDI connections on iOS.

## Getting Started

This plugin is build using Swift and Kotlin on the native side, so make sure your project supports this.

- Get a list of available MIDI devices by calling `MidiCommand().devices` which returns a list of `MidiDevice`
- Start scanning for BLE MIDI devices by calling `MidiCommand().scanForBluetoothDevices()`
- Listen for updates in the MIDI setup by subscribing to `MidiCommand().onMidiSetupChanged`
- Connect to a specific `MidiDevice` by calling `MidiCommand.connectToDevice(selectedDevice)`
- Disconnect from the current device by calling `MidiCommand.disconnectDevice()`
- Listen for incoming MIDI messages on from the current device by subscribing to `MidiCommand().onMidiDataReceived`, after which the listener will recieve inbound MIDI messages as an UInt8List of variable length.
- Send a MIDI message by calling `MidiCommand.sendData(data)`, where data is an UInt8List of bytes following the MIDI spec.
- Or use the static `MidiCommandHelper` functions to send PC, CC, NoteOn and NoteOff messsages.

See example folder for how to use.

For help getting started with Flutter, view our online
[documentation](https://flutter.io/).

For help on editing plugin code, view the [documentation](https://flutter.io/developing-packages/#edit-plugin-package).

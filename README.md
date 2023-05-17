# BLEapp

# BLE Starter App for Android

This is a sample Android application that demonstrates scanning for nearby Bluetooth Low Energy (BLE) devices and establishing connections with them. The app utilizes the Android Bluetooth API to perform BLE operations.

## Features

- Scan for nearby BLE devices
- Display the scan results in a RecyclerView
- Connect to a selected BLE device
- Handle connection events, such as successful connection and disconnection
- Navigate to a separate activity for BLE operations with the connected device

## Prerequisites

Before running the app, ensure that you have the following:

- Android Studio installed on your machine
- An Android device with BLE capabilities for testing (or use an emulator that supports BLE)

## Getting Started

1. Clone the repository to your local machine.
2. Open the project in Android Studio.
3. Connect your Android device to your machine or launch an emulator.
4. Build and run the app on your device/emulator.

## Usage

Upon launching the app, you will see a screen with a "Start Scan" button. Tap the button to begin scanning for nearby BLE devices. The scan results will be displayed in a list below the button.

To connect to a specific device, tap on the device in the list. The app will initiate a connection with the selected device and navigate to a new screen for BLE operations.

If the app fails to connect to a device or the connection is lost, a prompt will be shown indicating the disconnection.

## Permissions

The app requires the following permissions:

- `ACCESS_FINE_LOCATION`: Required for scanning BLE devices on Android 6.0 (Marshmallow) and above.

When you first run the app, it may prompt you to grant the necessary permissions. Make sure to allow the requested permissions to enable BLE scanning.

## Dependencies

The app uses the following dependencies:

- [Timber](https://github.com/JakeWharton/timber): A logging utility for Android.
- [Anko](https://github.com/Kotlin/anko): A library for writing Kotlin code in a more concise and idiomatic way.

## Troubleshooting

If you encounter any issues or errors while running the app, consider the following:

- Make sure your Android device or emulator supports BLE.
- Ensure that Bluetooth is enabled on your device.
- Verify that the required permissions are granted for the app.
- Check the logcat output in Android Studio for any error messages or exceptions.

## Contributing

Contributions to this project are welcome. If you find any bugs, have feature requests, or want to make improvements, please open an issue or submit a pull request.



Please note that the README.md file assumes you have the necessary dependencies (`Timber` and `Anko`) included in your project. If you don't, you may need to remove or update the corresponding sections in the README file.

# Characteristic Adapter for RecyclerView in BLE Starter App for Android

The `CharacteristicAdapter` is a custom RecyclerView adapter used in the BLE Starter App for Android to display Bluetooth GATT characteristics in a list. It provides the necessary functionality to bind the characteristics to the view and handle click events on the items.

## Usage

To use the `CharacteristicAdapter` in your project, follow these steps:

1. Copy the `CharacteristicAdapter` class into your project's package structure.
2. Make sure you have the necessary dependencies imported in your project.
3. Create an instance of the `CharacteristicAdapter` by providing the list of `BluetoothGattCharacteristic` items and an `onClickListener` callback function.
4. Set the adapter to your RecyclerView by calling `recyclerView.adapter = characteristicAdapter`.

Here's an example of how to use the `CharacteristicAdapter`:

```kotlin
// Create a list of BluetoothGattCharacteristic items
val characteristicList: List<BluetoothGattCharacteristic> = ...

// Define an onClickListener callback for handling click events on the items
val onClickListener: (characteristic: BluetoothGattCharacteristic) -> Unit = { characteristic ->
    // Handle the click event for the selected characteristic
    // ...
}

// Create an instance of the CharacteristicAdapter
val characteristicAdapter = CharacteristicAdapter(characteristicList, onClickListener)

// Set the adapter to your RecyclerView
recyclerView.adapter = characteristicAdapter
```

Make sure to replace `characteristicList` with your actual list of `BluetoothGattCharacteristic` items and implement the appropriate logic in the `onClickListener` to handle the click events.

## Customization

The `CharacteristicAdapter` uses the `row_characteristic.xml` layout file to define the appearance of each item in the RecyclerView. You can customize the layout by modifying the XML file according to your needs.

## Dependencies

The `CharacteristicAdapter` has the following dependencies:

- `androidx.recyclerview.widget.RecyclerView`: The RecyclerView library used for displaying the list of characteristics.
- `kotlinx.android.synthetic.main.row_characteristic`: The synthetic imports used to access views in the XML layout file.

Make sure to have these dependencies included in your project.

## License

This project is licensed under the [MIT License](LICENSE).

## Contributing

Contributions to this project are welcome. If you find any bugs, have feature requests, or want to make improvements, please open an issue or submit a pull request.

## About

The `CharacteristicAdapter` was developed as part of the BLE Starter App for Android, which is an open-source project. It is maintained by Punch Through and is designed to provide a starting point for Android app developers working with Bluetooth Low Energy (BLE) devices.

For more information, visit the [Punch Through website](https://punchthrough.com) or check out the [GitHub repository](https://github.com/PunchThrough/ble-starter-android).

For any inquiries or support related to the BLE Starter App, please contact Punch Through through their official channels.

# Scan Result Adapter for RecyclerView in BLE Starter App for Android

The `ScanResultAdapter` is a custom RecyclerView adapter used in the BLE Starter App for Android to display scan results of Bluetooth Low Energy (BLE) devices in a list. It provides the necessary functionality to bind the scan results to the view and handle click events on the items.

## Usage

To use the `ScanResultAdapter` in your project, follow these steps:

1. Copy the `ScanResultAdapter` class into your project's package structure.
2. Make sure you have the necessary dependencies imported in your project.
3. Create an instance of the `ScanResultAdapter` by providing the list of `ScanResult` items and an `onClickListener` callback function.
4. Set the adapter to your RecyclerView by calling `recyclerView.adapter = scanResultAdapter`.

Here's an example of how to use the `ScanResultAdapter`:

```kotlin
// Create a list of ScanResult items
val scanResultList: List<ScanResult> = ...

// Define an onClickListener callback for handling click events on the items
val onClickListener: (device: ScanResult) -> Unit = { scanResult ->
    // Handle the click event for the selected scan result
    // ...
}

// Create an instance of the ScanResultAdapter
val scanResultAdapter = ScanResultAdapter(scanResultList, onClickListener)

// Set the adapter to your RecyclerView
recyclerView.adapter = scanResultAdapter
```

Make sure to replace `scanResultList` with your actual list of `ScanResult` items and implement the appropriate logic in the `onClickListener` to handle the click events.

## Customization

The `ScanResultAdapter` uses the `row_scan_result.xml` layout file to define the appearance of each item in the RecyclerView. You can customize the layout by modifying the XML file according to your needs.

## Dependencies

The `ScanResultAdapter` has the following dependencies:

- `androidx.recyclerview.widget.RecyclerView`: The RecyclerView library used for displaying the list of scan results.
- `kotlinx.android.synthetic.main.row_scan_result`: The synthetic imports used to access views in the XML layout file.

Make sure to have these dependencies included in your project.


# Bluetooth Low Energy (BLE) Connection Manager

The Bluetooth Low Energy (BLE) Connection Manager is a module that provides an interface for managing connections and performing operations with Bluetooth devices. It simplifies the process of connecting to BLE devices, discovering services, reading and writing characteristics, enabling and disabling notifications, and more.

## Features

- Connect to a Bluetooth device
- Disconnect from a Bluetooth device
- Discover services on a connected device
- Read and write characteristics of a device
- Enable and disable notifications for characteristics
- Request MTU (Maximum Transmission Unit) update for better data throughput
- Handle bond state changes for devices

## Usage

The Connection Manager is implemented as a singleton object called `ConnectionManager`. You can use the provided functions to perform various BLE operations.

### Connecting to a Device

To connect to a Bluetooth device, use the `connect` function:

kotlin
ConnectionManager.connect(device, context)
Make sure to pass the Bluetooth device and the application context as parameters.

#Performing BLE Operations
The Connection Manager provides functions for performing various BLE operations, such as reading and writing characteristics, enabling and disabling notifications, and more. Here are a few examples:

#Reading a characteristic:
ConnectionManager.readCharacteristic(device, characteristic)
#Writing to a characteristic:
ConnectionManager.writeCharacteristic(device, characteristic, payload)
#Enabling notifications for a characteristic:
ConnectionManager.enableNotifications(device, characteristic)
#Disabling notifications for a characteristic:
ConnectionManager.disableNotifications(device, characteristic)

Listening to Connection Events
You can register a listener to receive connection-related events, such as onConnectionSetupComplete, onDisconnect, onCharacteristicRead, onCharacteristicWrite, and more. Here's an example of registering a listener:

ConnectionManager.registerListener(listener)


Make sure to implement the ConnectionEventListener interface and provide the necessary callback functions.

Dependencies
The following dependencies are required for the Bluetooth Low Energy Connection Manager:

- android.bluetooth.BluetoothDevice
- android.bluetooth.BluetoothGatt
- android.bluetooth.BluetoothGattCallback
- android.bluetooth.BluetoothGattCharacteristic
- android.bluetooth.BluetoothGattDescriptor
- android.bluetooth.BluetoothGattService
- android.bluetooth.BluetoothProfile
- android.content.BroadcastReceiver
- android.content.Context
- android.content.Intent
- android.content.IntentFilter
- android.os.Handler
- android.os.Looper
- timber.log.Timber
Make sure to include these dependencies in your project.

# BLE Operations Activity in BLE Starter App for Android

The `BleOperationsActivity` is an activity in the BLE Starter App for Android that allows users to perform various Bluetooth Low Energy (BLE) operations on a connected device. It provides functionality for reading, writing, enabling notifications, and changing the MTU value of characteristic(s) of the connected device.

## Usage

To use the `BleOperationsActivity` in your project, follow these steps:

1. Copy the `BleOperationsActivity` class into your project's package structure.
2. Make sure you have the necessary dependencies imported in your project.
3. Launch the `BleOperationsActivity` by passing the `BluetoothDevice` object to it when starting the activity.

Here's an example of how to launch the `BleOperationsActivity`:

```kotlin
val bluetoothDevice: BluetoothDevice = ...

val intent = Intent(context, BleOperationsActivity::class.java)
intent.putExtra(BluetoothDevice.EXTRA_DEVICE, bluetoothDevice)
startActivity(intent)
```

Make sure to replace `bluetoothDevice` with your actual `BluetoothDevice` object.

## Functionality

The `BleOperationsActivity` provides the following functionality:

- Reading characteristic value: Allows the user to read the value of a selected characteristic.
- Writing characteristic value: Enables the user to write a custom payload to a writable characteristic.
- Enabling/Disabling notifications: Allows the user to toggle notifications for a characteristic, receiving value change notifications when enabled.
- Changing MTU value: Enables the user to request a change in the Maximum Transmission Unit (MTU) size for improved data transfer efficiency.

## Dependencies

The `BleOperationsActivity` has the following dependencies:

- `androidx.appcompat.app.AppCompatActivity`: The base activity class used for implementing the BLE operations activity.
- `android.bluetooth.BluetoothDevice`: The BluetoothDevice class for representing a remote Bluetooth device.
- `android.bluetooth.BluetoothGattCharacteristic`: The BluetoothGattCharacteristic class for representing a GATT characteristic.
- `android.view.inputmethod.InputMethodManager`: The InputMethodManager class for managing the input methods (e.g., keyboard).
- `android.widget.EditText`: The EditText class for providing text input capabilities.
- `androidx.recyclerview.widget.RecyclerView`: The RecyclerView class for displaying lists of items.
- `org.jetbrains.anko.alert`: The Anko library function for showing alert dialogs.
- `org.jetbrains.anko.selector`: The Anko library function for showing a selection dialog.
- `org.jetbrains.anko.yesButton` and `org.jetbrains.anko.noButton`: The Anko library functions for creating dialog buttons.

Make sure to have these dependencies included in your project.

## Customization

The `BleOperationsActivity` uses various layout files (`activity_ble_operations.xml`, `row_characteristic.xml`, `row_scan_result.xml`, `edittext_hex_payload.xml`) to define the appearance of the activity and its components. You can customize these layout files or modify the activity code to suit your specific requirements.

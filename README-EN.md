[繁體中文](README.md)

# Unity Timer

This is a lightweight timer utility for Unity games. It provides a simple API that allows you to create timers, set durations, start and stop timers, and register timer callbacks. It is based on [UniTask](https://github.com/Cysharp/UniTask) and implemented using `async/await` syntax in `C# 7.0`.

## Installation

### Method 1: Using Unity Package Manager (Recommended)
You can install this package directly via Unity Package Manager (UPM) using a Git URL:

1. Open Unity and go to `Window` -> `Package Manager`.
2. Click the `+` button in the top-left corner and select **"Add package from git URL..."**.
3. Enter the following Git URL and click **"Add"**: `https://github.com/hhs456/com.toolkid.unitytimer.git`
4. Unity will automatically download and install `Unity-Timer`, and you will find it under `Packages`.

### Method 2: Manual Installation
You can also integrate the Timer into your Unity project manually:

1. Download the [com.toolkid.unitytimer](https://github.com/hhs456/com.toolkid.unitytimer) repository from GitHub.
2. Copy the `Timer.cs` file into your Unity project's `Assets` folder.

## Usage

### Creating a Timer

To create a timer, simply instantiate a new `Timer` object in Unity and set the duration:

```csharp
Timer timer = new Timer(10f); // Set duration to 10 seconds
```

### Registering Callbacks

To register callbacks while the timer is running, subscribe to the `OnTimerTick` and `OnTimerComplete` events:

```csharp
timer.OnTimerTick += OnTick; // Register tick callback
timer.OnTimerComplete += OnComplete; // Register completion callback
```

In the `OnTick` method, you can update the UI or perform other necessary actions. In the `OnComplete` method, you can execute any required cleanup operations.

### Starting and Stopping the Timer

Start the timer:

```csharp
timer.Start();
```

Stop the timer:

```csharp
timer.Stop();
```

### Notes

During the timer's runtime, the `OnTimerTick` event is triggered every 0.1 seconds until the timer completes. When the timer finishes, the `OnTimerComplete` event will be triggered.
Contributing

If you find any issues or would like to contribute, please create an issue or submit a pull request on `GitHub`.

### License

This timer is licensed under the [MIT](https://choosealicense.com/licenses/mit/) license. See the `LICENSE` file for more details.

### Acknowledgments

Thanks to [UniTask](https://github.com/Cysharp/UniTask) for providing the `async/await` functionality, making it easier to work with timers. Special thanks to the developers of [UniTask](https://github.com/Cysharp/UniTask) for their outstanding tool.

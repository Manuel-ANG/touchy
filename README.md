>This is my undergraudate project so it is meant to be used for research but not for production. You can freely inspire yourself by looking at the code but trying to use for production, I wouldn't do it. 


# Touchy

Touchy is an Android library that intercepts all touch events and lets you access those intercepted touch events from a single place.

There are different ways to capture touch events in Android such as setting listeners to views or overriding the related methods but there is no unified/single way to do this for the whole application. 

Touchy provides this application-wide solution. It is also super easy to use.

## Setup

Just add it as a dependency.

```Java
implementation 'fun.observe:touchy:1.0.0'
```

## Usage

Create a new *MotionEventReceiver* object and register it to the *MotionEventBroadcaster*. Do your work inside the *onReceive* method.

```Java
MotionEventBroadcaster.registerReceiver(new MotionEventReceiver() {
    @Override
    protected void onReceive(MotionEvent motionEvent) {
        Log.d(TAG, motionEvent.toString());
    }
});

```

***Note:*** You can register a receiver in a lifecycle-aware way. If you do it, do not forget to unregister the receiver. Touchy uses LiveData behind the scenes.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update the tests as appropriate.

## License
[GNU GPLv3](https://choosealicense.com/licenses/gpl-3.0/)

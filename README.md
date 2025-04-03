This is essentially a fork of https://github.com/flutter/packages/tree/main/packages/camera/camera_avfoundation

However, due to how flutter manages their packages, it's just copied into this directory.
We modify `availableCamerasWithCompletion` in `CameraPlugin.m` to set `discoveryDevices` to
```
    NSMutableArray *discoveryDevices =
                [@[ AVCaptureDeviceTypeBuiltInWideAngleCamera, 
            AVCaptureDeviceTypeBuiltInTelephotoCamera,
            AVCaptureDeviceTypeBuiltInDualCamera,
            AVCaptureDeviceTypeBuiltInDualWideCamera,
            AVCaptureDeviceTypeBuiltInTripleCamera  ]
            mutableCopy];
```

We do this because we want access to the logical cameras that iOS provides.

Also see https://github.com/flutter/flutter/issues/134151
# FaceTracking
An example app with AVFoundation camera support and face features tracking written in Swift 3.0.

Below an example how it works.

<img src="https://github.com/pranavansp/FaceTracking/blob/master/app_example_track.PNG" width="300">


# Store image on Device
Caliing below function will help you to store image on device.
```swift
func saveToCamera() {
        
        if let videoConnection = stillImageOutput.connection(withMediaType: AVMediaTypeVideo) {
            
            stillImageOutput.captureStillImageAsynchronously(from: videoConnection, completionHandler: { (CMSampleBuffer, Error) in
                if let imageData = AVCaptureStillImageOutput.jpegStillImageNSDataRepresentation(CMSampleBuffer) {
                    
                    if let cameraImage = UIImage(data: imageData) {
                        
                        UIImageWriteToSavedPhotosAlbum(cameraImage, nil, nil, nil)
                    }
                }
            })
        }
    }
```  
    
If this code was helpful, I would love to hear from you.
Twitter : [@Pranavan](http://twitter.com/ImPrana) <br/>

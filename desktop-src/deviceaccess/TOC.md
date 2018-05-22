# [Device Access API](device-access-broker-api-portal.md)
## [About the Device Access API](about-the-device-access-api.md)
## [How to Use the Device Access API](using-the-device-access-api.md)
### [Design Considerations for Custom Devices](design.md)
### [Implement the Device Access Object](create-the-device-access-object.md)
### [Declaring the Device Capability](declaring-the-device-capability.md)
### [Register the device interface as restricted to privileged apps](register-the-device-interface-class-as-privileged.md)
### [Create a Windows Runtime Extension](create-a-windows-runtime-extension.md)
## [Device Access API C++ Programming Reference](device-access-api-c---programming-reference.md)
### [Functions](functions.md)
#### [CreateDeviceAccessInstance](/windows/win32/content/deviceaccess/nf-deviceaccess-createdeviceaccessinstance?branch=dev)
### [COM Interfaces](com-interfaces.md)
#### [ICreateDeviceAccessAsync](/windows/win32/content/Deviceaccess/nn-deviceaccess-icreatedeviceaccessasync?branch=dev)
##### [Cancel Method](/windows/win32/content/Deviceaccess/nf-deviceaccess-icreatedeviceaccessasync-cancel?branch=dev)
##### [Wait Method](/windows/win32/content/Deviceaccess/nf-deviceaccess-icreatedeviceaccessasync-wait?branch=dev)
##### [Close Method](/windows/win32/content/Deviceaccess/nf-deviceaccess-icreatedeviceaccessasync-close?branch=dev)
##### [GetResult Method](/windows/win32/content/Deviceaccess/nf-deviceaccess-icreatedeviceaccessasync-getresult?branch=dev)
#### [IDeviceIoControl](/windows/win32/content/Deviceaccess/nn-deviceaccess-ideviceiocontrol?branch=dev)
##### [DeviceIoControlSync Method](/windows/win32/content/Deviceaccess/nf-deviceaccess-ideviceiocontrol-deviceiocontrolsync?branch=dev)
##### [DeviceIoControlAsync Method](/windows/win32/content/Deviceaccess/nf-deviceaccess-ideviceiocontrol-deviceiocontrolasync?branch=dev)
##### [CancelOperation Method](/windows/win32/content/Deviceaccess/nf-deviceaccess-ideviceiocontrol-canceloperation?branch=dev)
#### [IDeviceRequestCompletionCallback](/windows/win32/content/Deviceaccess/nn-deviceaccess-idevicerequestcompletioncallback?branch=dev)
##### [RequestCompletion Method](/windows/win32/content/deviceaccess/nf-deviceaccess-idevicerequestcompletioncallback-requestcompletion?branch=dev)
## [Device Access Glossary](deviceaccess-glossary.md)
## [Other APIs](other-apis.md)
### [DeviceInterfaceClassAccessCheckWithCallingThread method](ideviceaccesspolicycheck-deviceinterfaceclassaccesscheckwithcallingthread.md)
### [OpenDeviceFromInterfacePath method](idevicebroker-opendevicefrominterfacepath.md)

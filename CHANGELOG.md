Change Log
==========

v2.0.3
- Add tags 115, 116, 121, 122,128, 138, 139

v2.0.2
- Add ToDetailed method

v2.0.1
- Add ConvertTargetCenterPoint
- Fix Tag 110
- Fix Unsigned/signed range exception

v2.0.0
- Add multi-instance support
- Add VObject to VMTI

Breaking changes:
- ref, readonly ref, in, out not allowed as parameters or return on methods with Unmanaged callers only. Introduced in .NET SDK 6.0.200, Visual Studio 2022 version 17.1. So, the interface of Encode method has been changed.

v1.4.1
- First release

v1.3.0
- Initial version
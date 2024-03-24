Change Log
==========

### Ver. 2.3.0 (21/03/24)
- Remove length from VMTI Location (tag 17)
- Remove length from VMTI Velocity and Acceleration DLP 

### Ver. 2.2.1 (10/03/23)
- Generic Flag Data (tag47) Versions 13 through 16 of ST 0601 unintentionally inverted the column definitions; 

### Ver. 2.2.0 (07/11/23)
- Bump the version to 2.2.0 to sync with the native library

v2.1.1 (16/07/23)
- Fix BER-OID Encoding/Decoding for VMTI Target ID

v2.1.0
- Add VChip support

v2.0.5
- Add some new methods to the library

v2.0.4
- Fix VMTI target id

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
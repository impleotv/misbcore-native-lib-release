v2.0.0

- Add multi-instance support
- Add VObject to VMTI

Breaking changes:
- "ref, readonly ref, in, out not allowed as parameters or return on methods with Unmanaged callers only". Introduced in .NET SDK 6.0.200, Visual Studio 2022 version 17.1. So, the interface of Encode method has been changed. It now returns a structure with both buffer pointer + lenght


v1.4.1

- First release


v1.3.0

- Initial version
v2.5.0 (12/08/24)
- MISB 903.6 (VMTI) additions
- Add VMTI VTarget Pack Tag 22 (algorithmId) 
- Add VMTI AlgorithmSeries Tag 102 support 
- Add VMTI OntologySeries Tag 103 support 
- Add VMTI vTargetSeries (tag 101) vObjectSeries Tag 107 support 
- Add VMTI vTargetSeries (tag 101) vChipSeries Tag 106 support 

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
- "ref, readonly ref, in, out not allowed as parameters or return on methods with Unmanaged callers only". Introduced in .NET SDK 6.0.200, Visual Studio 2022 version 17.1. So, the interface of Encode method has been changed. It now returns a structure with both buffer pointer + length


v1.4.1
- First release

v1.3.0
- Initial version
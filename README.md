
<div align="center">
  <a >
    <img src="images/impleo_logo.png" alt="Logo" >
  </a>
</div>

# MisbCoreNative Lib

**MisbCoreNative Lib** is a KLV / MISB metadata encoder / decoder compiled as a self-contained native library (Native AOT Form Factor).  
It allows an easy integration of [MisbCore library](https://www.impleotv.com/content/misbcore/help/index.html) into C/C++ cross-platform applications.  

More info on [MisbCoreNative Lib](https://www.impleotv.com/content/misbcore/help/user-guide/native-lib/).  

## System Requirements
OS: Windows / Linux. x64 bit only.

## Installation

**MisbCoreNative Lib** can be downloaded as a **zip** file for particular operation system:  
 - MisbCoreNativeLib-windows-x64.zip  - Windows
 - MisbCoreNativeLib-linux-x64.zip   - Linux

## Download links

|          | Version             | Download link                                                           | 
|:---------|:-------------------:|:------------------------------------------------------------------------|
| **MisbCoreNativeLib windows-x64**   |  master | [MisbCoreNativeLib-windows-x64.zip](https://github.com/impleotv/misbcore-native-lib-release/releases/latest/download/MisbCoreNativeLib-windows-x64.zip) | 
| **MisbCoreNativeLib linux-x64**     |  master | [MisbCoreNativeLib-linux-x64.zip](https://github.com/impleotv/misbcore-native-lib-release/releases/latest/download/MisbCoreNativeLib-linux-x64.zip)   | 
| **MisbCoreNativeLib linux-arm64**   |  master | [MisbCoreNativeLib-linux-arm64.zip](https://github.com/impleotv/misbcore-native-lib-release/releases/latest/download/MisbCoreNativeLib-linux-arm64.zip)   | 

*Released on Tue, 22 Mar, 17:22 GMT+2*

## License

**MisbCoreNative Lib** is a node locked software. In order to get the license, please install it and fill an [online form](https://docs.google.com/forms/d/e/1FAIpQLSd_XW6bDsFce1G1cpds4gMQNlwNax0CvkWzcMbscxZ5rLaIbA/viewform), providing the ***Node Info*** string (IMPORTANT!!!) for the target machine.  
***Node Info*** string can be obtained by calling **GetNodeInfo** method, as shown below.

```cpp
typedef char* (*getNodeInfoFunc)();

getNodeInfoFunc GetNodeInfo = (getNodeInfoFunc)funcAddr(handle, (char*)"GetNodeInfo");
char* nodeInfo = GetNodeInfo();
printf("The NodeInfo: %s \n", nodeInfo);
```
We'll send you back the **license** file and a **key**.  
You can then activate the instance by calling **Activate** method:  

```cpp
#ifdef _WIN32
    #define funcAddr GetProcAddress
    HINSTANCE handle = LoadLibraryA((char*)PathToLibrary);
#else
    #define funcAddr dlsym
    void* handle = dlopen((char*)PathToLibrary, RTLD_LAZY);
#endif

const char* PathToLicenseFile = "/home/user/Licenses/Impleo/MisbCoreNativeLicense.lic";
const char* LicenseKey = "AF596BF0-BBAB142B-1B905B24-8DA51BED";
typedef bool (*activateFunc)(char*, char*);

activateFunc Activate = (activateFunc)funcAddr(handle, (char*)"Activate");
bool fValid = Activate((char*)PathToLicenseFile, (char*)LicenseKey);
```
> For large quantities, please contact us for an **unlocked license**.

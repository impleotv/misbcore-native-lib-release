
<div align="center">
  <a >
    <img src="images/impleo_logo.png" alt="Logo" >
  </a>
</div>

# MisbCoreNative Lib

**MisbCoreNative Lib** is a KLV / MISB metadata encoder / decoder compiled as a self-contained native library (Native AOT Form Factor).  
It allows an easy integration of [MisbCore library](https://www.impleotv.com/content/misbcore/help/index.html) into C/C++ cross-platform applications.

## System Requirements
OS: Windows / Linux. 64 bit only.

## Installation

**MisbCoreNative Lib**  can be downloaded as a **zip** file for particular operation system:  
 - MisbCoreNativeLib.dll.zip  - Windows
 - MisbCoreNativeLib.so.zip   - Linux

## Download links

|          | Version             | Download link                                                           | 
|:---------|:-------------------:|:------------------------------------------------------------------------|
| **MisbCoreNativeLib.dll** |  master | [MisbCoreNativeLib.dll.zip](https://github.com/impleotv/misbcore-native-lib-release/releases/latest/download/MisbCoreNativeLib.dll.zip) | 
| **MisbCoreNativeLib.so**  |  master | [MisbCoreNativeLib.so.zip](https://github.com/impleotv/misbcore-native-lib-release/releases/latest/download/MisbCoreNativeLib.so.zip)   | 

*Released on Mon, 6 Dec, 09:45 GMT+2*


## License

**MisbCoreNative Lib** is a node locked software. In order to get the license, please install it and fill an [online form](https://docs.google.com/forms/d/e/1FAIpQLSd_XW6bDsFce1G1cpds4gMQNlwNax0CvkWzcMbscxZ5rLaIbA/viewform), providing the ***Node Info*** string (IMPORTANT!!!) for the target machine.  
***Node Info*** string can be obrtained by calling **GetNodeInfo** method, as shown below.

```cpp
typedef char* (*getNodeInfoFunc)();

getNodeInfoFunc GetNodeInfo = (getNodeInfoFunc)funcAddr(handle, (char*)"GetNodeInfo");
char* nodeInfo = GetNodeInfo();
printf("The NodeInfo: %s \n", nodeInfo);
```

We'll send you back the **license** file and a **key**.  
You can then activate the instance by calling **Activate** method:  

```cpp
  const char* PathToLicenseFile = "/home/user/Licenses/Impleo/MisbCoreNativeLicense.lic";
  const char* LicenseKey = "AF596BF0-BBAB142B-1B905B24-8DA51BED";
  typedef bool (*activateFunc)(char*, char*);

	activateFunc Activate = (activateFunc)funcAddr(handle, (char*)"Activate");
	bool fValid = Activate((char*)PathToLicenseFile, (char*)LicenseKey);
```

> For large quantities, please contact us for an **unlocked license**.

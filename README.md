
<div align="center">
  <a >
    <img src="images/impleo_logo.png" alt="Logo" >
  </a>
</div>

# MisbCoreNative Lib (libmisbcore)

**libmisbcore** is a KLV / MISB metadata encoder / decoder compiled as a self-contained native library (Native AOT Form Factor).  
It allows easy integration of [MisbCore library](https://www.impleotv.com/content/misbcore/help/index.html) into C/C++ cross-platform applications.  

More info on [MisbCoreNative Lib](https://www.impleotv.com/content/misbcore/help/user-guide/native-lib/).  
Samples [MisbCoreNative sample apps](https://www.impleotv.com/content/misbcore-native-samples/help/).  

## System Requirements
OS: Windows x64 / Linux (x64, arm64).

## Download links

|          | Version             | Download link                                                           | 
|:---------|:-------------------:|:------------------------------------------------------------------------|
| **libmisbcore linux-x64**      |  v3.0.0 | [libmisbcore_v3.0.0_amd64.deb](https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.0/libmisbcore_v3.0.0_amd64.deb)   | 
| **libmisbcore linux-arm64**    |  v3.0.0 | [libmisbcore_v3.0.0_arm64.deb](https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.0/libmisbcore_v3.0.0_arm64.deb)   | 
| **libmisbcore win-x64**        |  v3.0.0 | [libmisbcore_v3.0.0_win-x64.zip](https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.0/libmisbcore_v3.0.0_win-x64.zip) | 
| **libmisbcore C demo app**     |  v3.0.0 | [libmisbcore_-demo.zip](https://github.com/impleotv/misbcore-native-lib-release/releases/latest/download/MisbCoreNativeLib-demo.zip)   | 

*Released on Tue, 1 Jul, 19:18 GMT+3*


## Install with the .deb file (x64)

```
wget -O /tmp/libmisbcore.deb https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.0/libmisbcore_v3.0.0_amd64.deb  
sudo dpkg -i /tmp/libmisbcore.deb  
rm /tmp/libmisbcore.deb
```
## Install with the .deb file (arm64)

```
wget -O /tmp/libmisbcore.deb https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.0/libmisbcore_v3.0.0_arm64.deb 
sudo dpkg -i /tmp/libmisbcore.deb  
rm /tmp/libmisbcore.deb
```

Check with dpkg:  

```
dpkg -l | grep libmisbcore
```

You should see a line like:  
```
ii  libmisbcore  2.7.0 amd64 Native MISB 601 core processing library
```

Show detailed status of the package:  

```
dpkg -s libmisbcore
```

To remove the library

```
sudo apt remove libmisbcore
```

or 

```
sudo dpkg -r libmisbcore
```

## License

**libmisbcore**  is a node-locked software. To obtain a license, install the library and complete the the [online form](https://docs.google.com/forms/d/e/1FAIpQLSd_XW6bDsFce1G1cpds4gMQNlwNax0CvkWzcMbscxZ5rLaIbA/viewform),
including the Node Info string (this is required). 

You can obtain the **Node Info** string in one of two ways:

## By running the **misbcore-ni** app.

> Note: You must install the library before running the **misbcore-ni** application.  


## Download links

|                                | Download link                                                           | 
|:------------------------------:|:------------------------------------------------------------------------|
| **misbcore-ni linux-x64**      |  [misbcore-ni](https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.0/misbcore-ni_v3.0.0_linux-x64)   | 
| **misbcore-ni linux-arm64**    |  [misbcore-ni](https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.0/misbcore-ni_v3.0.0_linux-arm64)   | 
| **misbcore-ni win-x64**        |  [misbcore-ni.eve](https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.0/misbcore-ni_v3.0.0_win-x64.exe) | 



## By calling **GetNodeInfo** method in the code.

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


⚠️ ## Antivirus False Positives on AOT-Compiled Windows Libraries 

Because our Windows libraries are built using Native AOT (Ahead‑of‑Time) compilation,
some antivirus products may mistakenly detect them as malware (e.g. Trojan.Win64.XLoader, W64/Agent.KHK.gen, etc.).
This is a known issue: numerous reports confirm that scanning AOT executables on Windows triggers heuristic-based false positives - 
even though the exact same code compiled on Linux does not produce antivirus alerts.

Why this happens  
AOT compilation produces self-contained native binaries with embedded metadata and code patterns. 
Antivirus engines on Windows often use heuristic signatures that can misidentify these patterns as malicious, even though they’re harmless 
Native AOT on Linux uses different toolchains and binary formats, and such false positives are not observed there.

Why you can trust our builds  
All builds are performed entirely from source on a clean GitHub-hosted virtual machine.  
At no point is malware ever introduced or presen — so any antivirus flagging must be a false positive caused by the compilation format.

What this means for you  
- There is no real virus in our Windows libraries — only a known issue with antivirus heuristics targeting AOT binaries.  
- We’re continuously monitoring antivirus engine improvements, but there is nothing further we can do — the false positives stem from the AOT compilation itself.

If desired, you may:
- Use **.net** library on Windows, writing a wrapper for C/C++, if needed.
- Ask for Customer-Side Compilation. It's theoretically possible to compile the Windows libraries locally (on sustomer's premises). However, this setup incurs additional costs and overhead.







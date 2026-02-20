
<div align="center">
  <a >
    <img src="images/impleo_logo.png" alt="Logo" >
  </a>
</div>

# MisbCoreNative Lib (libmisbcore)

**libmisbcore** is a KLV/MISB metadata encoder and decoder, compiled as a self-contained native library (Native AOT form factor).
It enables easy integration of the [MisbCore library](https://www.impleotv.com/content/misbcore/help/index.html) into cross-platform C/C++ applications. 

More info on [libmisbcore](https://www.impleotv.com/content/misbcore/help/user-guide/native-lib.html).  
Samples [libmisbcore sample apps](https://www.impleotv.com/content/misbcore-native-samples/help/).  

## System Requirements
OS: Linux (x64, arm64) / Windows x64.

## Download links

|   Library                      | Version      | Download link                                                           | 
|:-------------------------------|:------------:|:------------------------------------------------------------------------|
| **libmisbcore linux-x64**      |  v3.0.1 | [libmisbcore_amd64.deb](https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.1/libmisbcore_amd64.deb)   | 
| **libmisbcore linux-arm64**    |  v3.0.1 | [libmisbcore_arm64.deb](https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.1/libmisbcore_arm64.deb)   | 
| **libmisbcore win-x64**        |  v3.0.1 | [libmisbcore_win-x64.zip](https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.1/libmisbcore_win-x64.zip) | 
| **libmisbcore C demo app**     |  v3.0.1 | [libmisbcore_-demo.zip](https://github.com/impleotv/misbcore-native-lib-release/releases/latest/download/demoApp.zip)   | 

*Released on Fri, 20 Feb 2026, 09:42 GMT+2*


## Install with the .deb file (x64)

```
wget -O ./libmisbcore.deb https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.1/libmisbcore_amd64.deb  
sudo dpkg -i ./libmisbcore.deb  
rm ./libmisbcore.deb
```
## Install with the .deb file (arm64)

```
wget -O ./libmisbcore.deb https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.1/libmisbcore_arm64.deb 
sudo dpkg -i ./libmisbcore.deb  
rm ./libmisbcore.deb
```

Check with dpkg:  

```
dpkg -l | grep libmisbcore
```

You should see a line like:  

*ii  libmisbcore  v3.0.1 amd64 Native MISB 601 core processing library*


Show detailed status of the package:  

```
dpkg -s libmisbcore
```

To remove the library:

```
sudo apt remove libmisbcore
```

or 

```
sudo dpkg -r libmisbcore
```

## Windows  

Copy **libmisbcore.dll** to your current directory or add its location to your system's PATH environment variable.


## License

**libmisbcore**  is a node-locked software. To obtain a license, install the library and complete the the [online form](https://docs.google.com/forms/d/e/1FAIpQLSd_XW6bDsFce1G1cpds4gMQNlwNax0CvkWzcMbscxZ5rLaIbA/viewform),
including the Node Info string (this is required). 

You can obtain the **Node Info** string by running the **misbcore-ni** app.

> Note: You must install the library before running the **misbcore-ni** application.  

## Download links
|   Application                      | Download link                                                           | 
|:-----------------------------------|:------------------------------------------------------------------------|
| **misbcore-ni for linux-x64**      |  [misbcore-ni_linux-x64](https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.1/misbcore-ni_linux-x64)   | 
| **misbcore-ni for linux-arm64**    |  [misbcore-ni_linux-arm64](https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.1/misbcore-ni_linux-arm64)   | 
| **misbcore-ni for win-x64**        |  [misbcore-ni-win-x64.exe](https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.1/misbcore-ni_win-x64.exe) | 


Make the application executable, then run it.  
For linux x64: 

```
wget -O ./misbcore-ni https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.1/misbcore-ni_linux-x64
sudo chmod +x misbcore-ni
./misbcore-ni
```

For linux arm64: 

```
wget -O ./misbcore-ni https://github.com/impleotv/misbcore-native-lib-release/releases/download/v3.0.1/misbcore-ni_linux-arm64
sudo chmod +x misbcore-ni
./misbcore-ni
```

<div align="center">
  <a >
    <img src="images/libmisbcore-qr.png" alt="qr" >
  </a>
</div>

Please either copy and paste the Node Info string or send us a photo of the QR code.

> For large quantities, please contact us for an **unlocked license**.


## ⚠️ GLIBC Compatibility Notice for libmisbcore.so

The **libmisbcore.so** library is compiled on Ubuntu 22.04, which includes GLIBC version 2.35 by default.
As a result, the compiled binary may require this GLIBC version or newer at runtime.

❗ Potential problem on Older Distributions
If you attempt to run the library on older Debian-based systems (such as Debian 10 or Ubuntu 18.04),
which include GLIBC versions like 2.27 or earlier, you may encounter error that indicates a runtime incompatibility between the library and the system’s C library.

✅ Recommended Solutions  

Depending on your environment and constraints, you may choose one of the following approaches:  

- Use an older Version of libmisbcore.so  
- Install a newer GLIBC in a Custom Location

🧪 Verifying Your System’s GLIBC Version  

Run the following command to check your installed GLIBC version:  

```
ldd --version
```

Need a Compatible Build?  
If none of the above options work for your use case, and your platform is restricted to older system libraries, contact us. We may be able to provide a custom build compiled against older toolchains, if justified.


## ⚠️ Antivirus False Positives on AOT-Compiled Windows Libraries 

Because the Windows library is built using Native AOT (Ahead‑of‑Time) compilation,
some antivirus products may mistakenly detect them as malware (e.g. Trojan.Win64.XLoader, W64/Agent.KHK.gen, etc.).
This is a known issue: numerous reports confirm that scanning AOT executables on Windows triggers heuristic-based false positives.
Linux does not produce antivirus alerts.

**Why this happens**  
AOT compilation produces self-contained native binaries with embedded metadata and code patterns. 
Antivirus engines on Windows often use heuristic signatures that can misidentify these patterns as malicious, even though they’re harmless 
Native AOT on Linux uses different toolchains and binary formats, and such false positives are not observed there.

**Why you can trust our builds**  
All builds are performed entirely from source on a clean GitHub-hosted virtual machine.  
At no point is malware ever introduced or presen, so any antivirus flagging must be a false positive caused by the compilation format.

**What this means for you**  
- There is no real virus in our Windows libraries, only a known issue with antivirus heuristics targeting AOT binaries.  
- We’re continuously monitoring antivirus engine improvements, but there is nothing further we can do — the false positives stem from the AOT compilation itself.

If desired, you may:
- Use **.net** library on Windows, writing a wrapper for C/C++, if needed.
- Ask for Customer-Side Compilation. While it is theoretically possible to compile the Windows libraries locally on the customer's premises, this approach involves additional costs and operational overhead.






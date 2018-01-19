# Ncnn-Installation-on-Windows
The steps and tips of installing the ncnn+protobuf envs on Windows.


----
#### Since the guide of installing and building Ncnn on Windows on the Official Site **can't** actually lead me correctly:

  https://github.com/Tencent/ncnn/wiki/cmake-VS2017-%E7%BC%96%E8%AF%91

#### I've found some other resources to build the Ncnn on my computer.
----
## 1: A Standalone Project

  https://github.com/liyemei/ncnn-windows-vs2013
  
This project doesn't rely on the envs. All the resources of the 3rd party are included in the project.

But it relys on the **VS201x v120 toolset**.

----
## 2: A Project based on Ncnn

  https://github.com/moli232777144/mtcnn_ncnn/blob/master/README.md

If the envs on your computer can't be compatible with the **1: A Standalone Project**,the project listed in the above can lead you successfully. There is the guide written in **markdown** to build the project. Following the guide, you can also build ncnn and protobuf as 3rd parties into the project.

### **Modification of the README.md**：
### (1) Protobuf:
#### (a) Download Protobuf:
##### Ncnn relys on Protobuf, as the auther of the Ncnn listed on the Ncnn's official site, I recommend you to use the version 3.4.0

  https://github.com/google/protobuf/archive/v3.4.0.zip

#### (b) Build Protobuf:
##### Unzip the resources of Protobuf, now the folder's default name is protobuf-3.4.0
##### Use the System command prompt:cmd.exe
##### Goto the folder"cmake"under the folder "protobuf-3.4.0", by:
  
```
cd YourOwnPath\protobuf-3.4.0
cd cmake
```

##### Create a new folder called "build", by:

```
mkdir build
cd build
```

##### Then build the Protobuf, by:

```
cmake .. -Dprotobuf_BUILD_TESTS=OFF -Dprotobuf_MSVC_STATIC_RUNTIME=OFF -G "Visual Studio 15 2017 Win64"
```

*Attention: The last param **"Visual Studio 15 2017 Win64"** is according to the Visual Studio on your computer. You need to modify it.

##### Use the File Explorer to open the protobuf.sln under the YourOwnPath\protobuf-3.4.0\cmake\build

##### Modify the platform to "Release" and "x64", and then build it.



* TBC

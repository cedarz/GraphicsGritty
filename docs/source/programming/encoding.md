# 编码问题

## 路径的编码

1. std::string类型在Windows下使用的是本地的ANSI编码
2. std::ifstream(std::string)不支持UTF-8编码的文件路径，Windows系统下支持std::ifstream(std::wstring), Windows 文件系统默认使用 UTF-16 编码
3. [ghc/filesystem](https://github.com/gulrak/filesystem)实现文件路径的编码转换
4. Kitware的CMake和VTK的SystemTools中打开文件的调用（FOpen），使用MultiByteToWideChar对UTF-8编码的多字节文件路径转换到UTF-16编码的宽字节文件路径


- [ANSI是什么编码？](https://www.cnblogs.com/malecrab/p/5300486.html)
- [How to open an std::fstream (ofstream or ifstream) with a unicode filename?](https://stackoverflow.com/questions/821873/how-to-open-an-stdfstream-ofstream-or-ifstream-with-a-unicode-filename)
- [_wfopen(Encoding::ToWindowsExtendedPath(file).c_str(), trimmedMode.c_str())](https://github.com/Kitware/CMake/blob/master/Source/kwsys/SystemTools.cxx#L998)
- [VTK SystemTools.cxx]()
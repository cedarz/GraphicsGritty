# 编码问题

## 路径的编码

1. std::string类型在Windows下使用的是本地的ANSI编码
2. std::ifstream(std::string)不支持UTF-8编码的文件路径，Windows系统下支持std::ifstream(std::wstring), Windows 文件系统默认使用 UTF-16 编码
3. [ghc/filesystem](https://github.com/gulrak/filesystem)实现文件路径的编码转换
4. Kitware的CMake和VTK的SystemTools中打开文件的调用（FOpen），使用MultiByteToWideChar对UTF-8编码的多字节文件路径转换到UTF-16编码的宽字节文件路径
5. nlohmann::json 不直接支持 std::wstring，因为 JSON 标准规定字符串必须是 UTF-8 编码的 std::string 类型。可以通过将 std::wstring 转换为 UTF-8 编码的 std::string 来处理 wstring。json中编码的路径读取为std::string,再转换到std::wstring或者ansi以供使用。


- [ANSI是什么编码？](https://www.cnblogs.com/malecrab/p/5300486.html)
- [How to open an std::fstream (ofstream or ifstream) with a unicode filename?](https://stackoverflow.com/questions/821873/how-to-open-an-stdfstream-ofstream-or-ifstream-with-a-unicode-filename)
- [Is wstring character is Unicode ? What happens during conversion?](https://stackoverflow.com/questions/27225196/is-wstring-character-is-unicode-what-happens-during-conversion)
- [_wfopen(Encoding::ToWindowsExtendedPath(file).c_str(), trimmedMode.c_str())](https://github.com/Kitware/CMake/blob/master/Source/kwsys/SystemTools.cxx#L998)
- [VTK SystemTools.cxx]()
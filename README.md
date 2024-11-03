
# XOR Static Library

The XOR Static Library is a C++ library designed to provide compile-time string obfuscation and secure formatted output functions. Key features include:

* Compile-Time String Obfuscation: Using XOR encryption, this library obfuscates string literals at compile time, enhancing security by preventing plaintext strings from appearing in the compiled binary. The library achieves this through constexpr templates, which encrypt strings during compilation and decrypt them at runtime. The XorStr and XorStrW macros make it easy to obfuscate string literals inline within your code.

* Secure Formatted Output Functions: Custom implementations of common formatted output functions (w_printf, w_printf_s, w_sprintf, and others) are provided to support formatted printing with improved safety. These functions accept variadic arguments and offer additional buffer handling, reducing risks associated with buffer overflows and format string vulnerabilities.

## Usage/Examples

```cpp
#include <iostream>
#include <XOR.h>

int main(int argc, const char* argv[])
{
    // Example using XorStr for char strings
    std::cout << XorStr("Hello World!") << std::endl;

    // Example using XorStrW for wide (wchar_t) strings
    std::wcout << XorStrW(L"Hello Wide World!") << std::endl;

    return 0;
}
```


## Compilation Guide for Visual Studio 2022

To compile and use the XOR Static Library in Visual Studio 2022, follow these steps:

1. Open Visual Studio 2022:
     - Start Visual Studio and open or create a new C++ project.

2. Add the XOR Static Library:
     - If the library is a header-only implementation, copy the XOR.h file directly into your project directory and include it in your source files.
     - If it's more complex and includes additional source files, add them to your project by right-clicking on your project in the Solution Explorer and selecting Add > Existing Item....

3. Configure Project Properties:
     - Right-click on your project in Solution Explorer and select Properties.
     - In Configuration Properties > C/C++ > General, add the path to the XOR library in the Additional Include Directories field if necessary.

4. Set C++ Standard:
     - In Configuration Properties > C/C++ > Language, set the C++ Language Standard to at least C++17, as constexpr templates are essential for compile-time string obfuscation.

5. Build the Project:
     - Build your project by selecting Build > Build Solution or by pressing Ctrl + Shift + B.

6. Run the Application:
     - Once the project builds successfully, run your application to see the obfuscated strings decrypted and printed to the console.

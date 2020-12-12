---
description: "Hakkında daha fazla bilgi edinin: nasıl yapılır: System:: String 'i standart dizeye dönüştürme"
title: "Nasıl yapılır: System::String'i Standart Dizeye Dönüştürme"
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, converting System::String to standard string
- string conversion, System::String
ms.assetid: 79e2537e-d4eb-459f-9506-0e738045b59e
ms.openlocfilehash: 2bcdaef743f2856f2db20dae8b804bb33546ea0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181338"
---
# <a name="how-to-convert-systemstring-to-standard-string"></a>Nasıl yapılır: System::String'i Standart Dizeye Dönüştürme

<xref:System.String> `std::string` `std::wstring` `PtrToStringChars` Vcclr. h içinde kullanmadan veya ' a dönüştürebilirsiniz.

## <a name="example"></a>Örnek

```cpp
// convert_system_string.cpp
// compile with: /clr
#include <string>
#include <iostream>
using namespace std;
using namespace System;

void MarshalString ( String ^ s, string& os ) {
   using namespace Runtime::InteropServices;
   const char* chars =
      (const char*)(Marshal::StringToHGlobalAnsi(s)).ToPointer();
   os = chars;
   Marshal::FreeHGlobal(IntPtr((void*)chars));
}

void MarshalString ( String ^ s, wstring& os ) {
   using namespace Runtime::InteropServices;
   const wchar_t* chars =
      (const wchar_t*)(Marshal::StringToHGlobalUni(s)).ToPointer();
   os = chars;
   Marshal::FreeHGlobal(IntPtr((void*)chars));
}

int main() {
   string a = "test";
   wstring b = L"test2";
   String ^ c = gcnew String("abcd");

   cout << a << endl;
   MarshalString(c, a);
   c = "efgh";
   MarshalString(c, b);
   cout << a << endl;
   wcout << b << endl;
}
```

```Output
test
abcd
efgh
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

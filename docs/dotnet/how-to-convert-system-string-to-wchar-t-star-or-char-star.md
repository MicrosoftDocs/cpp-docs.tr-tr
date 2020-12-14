---
description: "Hakkında daha fazla bilgi edinin: nasıl yapılır: System:: String 'i wchar_t * veya char * olarak dönüştürme"
title: "Nasıl yapılır: System::String'i wchar_t* veya char* olarak dönüştürme"
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- System::String, converting to char or wchar_t
- PtrToStringChars method
- System::String
- wchart type, converting System::String
- char data type, converting System::String to
ms.assetid: 385da01b-5649-4543-8076-e3e251243ff0
ms.openlocfilehash: 973d9c71e536865188dc03d88821dacce4b20e52
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198368"
---
# <a name="how-to-convert-systemstring-to-wchar_t-or-char"></a>Nasıl yapılır: System::String'i wchar_t* veya char* olarak dönüştürme

`PtrToStringChars`Vcclr. h içinde yerel veya dönüştürmek için kullanabilirsiniz <xref:System.String> `wchar_t *` `char *` .  Bu, CLR dizeleri dahili olarak Unicode olduğundan, her zaman geniş bir Unicode dize işaretçisi döndürür. Daha sonra aşağıdaki örnekte gösterildiği gibi geniş bir dönüştürme yapabilirsiniz.

## <a name="example"></a>Örnek

```cpp
// convert_string_to_wchar.cpp
// compile with: /clr
#include < stdio.h >
#include < stdlib.h >
#include < vcclr.h >

using namespace System;

int main() {
   String ^str = "Hello";

   // Pin memory so GC can't move it while native function is called
   pin_ptr<const wchar_t> wch = PtrToStringChars(str);
   printf_s("%S\n", wch);

   // Conversion to char* :
   // Can just convert wchar_t* to char* using one of the
   // conversion functions such as:
   // WideCharToMultiByte()
   // wcstombs_s()
   // ... etc
   size_t convertedChars = 0;
   size_t  sizeInBytes = ((str->Length + 1) * 2);
   errno_t err = 0;
   char    *ch = (char *)malloc(sizeInBytes);

   err = wcstombs_s(&convertedChars,
                    ch, sizeInBytes,
                    wch, sizeInBytes);
   if (err != 0)
      printf_s("wcstombs_s  failed!\n");

    printf_s("%s\n", ch);
}
```

```Output
Hello
Hello
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

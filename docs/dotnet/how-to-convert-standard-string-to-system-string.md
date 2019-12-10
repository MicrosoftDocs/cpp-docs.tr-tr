---
title: 'Nasıl yapılır: Standart Dizeyi System::String Olarak Dönüştürme'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, converting strings to System::String
- string conversion [C++], C++ Standard Library string
- strings [C++], converting
ms.assetid: 1fde79a0-9d0b-44e5-981b-e8f2676c199d
ms.openlocfilehash: 3714cf519bcffc41ce8bfcf646dea11654d22ae1
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988258"
---
# <a name="how-to-convert-standard-string-to-systemstring"></a>Nasıl yapılır: Standart Dizeyi System::String Olarak Dönüştürme

Bu konu başlığı altında, standart C++ bir kitaplık dizesinin ([\<dize >](../standard-library/string.md)) bir <xref:System.String>nasıl dönüştürüleceği gösterilmektedir.

## <a name="example"></a>Örnek

```cpp
// convert_standard_string_to_system_string.cpp
// compile with: /clr
#include <string>
#include <iostream>
using namespace System;
using namespace std;

int main() {
   string str = "test";
   cout << str << endl;
   String^ str2 = gcnew String(str.c_str());
   Console::WriteLine(str2);

   // alternatively
   String^ str3 = gcnew String(str.c_str());
   Console::WriteLine(str3);
}
```

```Output
test
test
test
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: Standart Dizeyi System:: String olarak dönüştürme'
title: 'Nasıl yapılır: Standart Dizeyi System::String Olarak Dönüştürme'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, converting strings to System::String
- string conversion [C++], C++ Standard Library string
- strings [C++], converting
ms.assetid: 1fde79a0-9d0b-44e5-981b-e8f2676c199d
ms.openlocfilehash: b42e321f7819bf61149e17b5281badf4704bdbfb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181364"
---
# <a name="how-to-convert-standard-string-to-systemstring"></a>Nasıl yapılır: Standart Dizeyi System::String Olarak Dönüştürme

Bu konu, bir C++ standart kitaplığı dizesinin () ' a nasıl dönüştürüleceğini gösterir [\<string>](../standard-library/string.md) <xref:System.String> .

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

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

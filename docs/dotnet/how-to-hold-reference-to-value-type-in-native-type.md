---
title: 'Nasıl yapılır: Yerel Tür İçinde Değer Türüne Başvuruyu Tutma'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- value type reference in native type
- reference to value type in native type
ms.assetid: 1eabf8be-7d4f-4339-9027-48d5c4244483
ms.openlocfilehash: 4b71701c771f6f49bae172284e23dd9eba2aeded
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988483"
---
# <a name="how-to-hold-reference-to-value-type-in-native-type"></a>Nasıl yapılır: Yerel Tür İçinde Değer Türüne Başvuruyu Tutma

Yerel bir türdeki bir değer türünün başvurusunu tutmak için kutulanmış tür üzerinde `gcroot` kullanın.

## <a name="example"></a>Örnek

```cpp
// reference_to_value_in_native.cpp
// compile with: /clr
#using <mscorlib.dll>
#include <vcclr.h>

using namespace System;

public value struct V {
   String ^str;
};

class Native {
public:
   gcroot< V^ > v_handle;
};

int main() {
   Native native;
   V v;
   native.v_handle = v;
   native.v_handle->str = "Hello";
   Console::WriteLine("String in V: {0}", native.v_handle->str);
}
```

```Output
String in V: Hello
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

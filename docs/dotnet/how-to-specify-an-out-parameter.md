---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: bir out parametresi belirtme'
title: 'Nasıl yapılır: Bir out parametresi belirtme'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
ms.openlocfilehash: b43930557b4bdfd22bf902a6d9adf95eb8ba4d01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286351"
---
# <a name="how-to-specify-an-out-parameter"></a>Nasıl yapılır: Bir out parametresi belirtme

Bu örnek, bir işlev parametresinin bir `out` parametre olduğunu ve C# programından bu işlevin nasıl çağrılacağını gösterir.

`out`C++ ' da kullanılarak bir parametre belirtilir <xref:System.Runtime.InteropServices.OutAttribute> .

## <a name="example"></a>Örnek

Bu örneğin ilk bölümü bir C++ DLL oluşturur. Parametresi olan bir işlev içeren bir türü tanımlar `out` .

```cpp
// cpp_out_param.cpp
// compile with: /LD /clr
using namespace System;
public value struct TestStruct {
   static void Test([Runtime::InteropServices::Out] String^ %s) {
      s = "a string";
   }
};
```

Bu kaynak dosya, önceki örnekte oluşturulan C++ bileşenini tüketen bir C# istemcidir.

```csharp
// cpp_out_param_2.cs
// compile with: /reference:cpp_out_param.dll
using System;
class TestClass {
   public static void Main() {
      String t;
      TestStruct.Test(out t);
      System.Console.WriteLine(t);
   }
}
```

```Output
a string
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

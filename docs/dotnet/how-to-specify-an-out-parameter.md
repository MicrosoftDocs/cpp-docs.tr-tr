---
title: 'Nasıl yapılır: bir out parametresi belirtme'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
ms.openlocfilehash: 4bd6ad1d3009adcc124bdeb90d9d67de07112de2
ms.sourcegitcommit: c4528a7424d35039454f17778baf1b5f98fbbee7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912791"
---
# <a name="how-to-specify-an-out-parameter"></a>Nasıl yapılır: bir out parametresi belirtme

Bu örnek, bir işlev parametresinin bir `out` parametresi olduğunu ve bu işlevin bir C# programdan nasıl çağrılacağını gösterir.

Bir `out` parametresi içinde C++ <xref:System.Runtime.InteropServices.OutAttribute> kullanılarak belirtilir.

## <a name="example"></a>Örnek

Bu örneğin ilk bölümü bir C++ dll oluşturur. `out` parametresine sahip bir işlev içeren bir türü tanımlar.

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

Bu kaynak dosya, önceki C# örnekte oluşturulan C++ bileşeni tüketen bir istemcidir.

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

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

---
title: 'Nasıl yapılır: Bir out Parametresini Belirleme'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
ms.openlocfilehash: 5f0b462e672de4408d50bf95d65c749bf1881078
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988432"
---
# <a name="how-to-specify-an-out-parameter"></a>Nasıl yapılır: Bir out Parametresini Belirleme

Bu örnek, bir işlev parametresinin out parametresi ve bu işlevin bir C# programdan nasıl çağrılacağını belirtir.

Bir out parametresi görselde C++ <xref:System.Runtime.InteropServices.OutAttribute> ile belirtilir.

## <a name="example"></a>Örnek

Bu örneğin ilk bölümü, out parametresine sahip bir C++ işlev içeren bir türe sahip bir Visual dll 'dir.

```cpp
// cpp_out_param.cpp
// compile with: /LD /clr:safe
using namespace System;
public value struct TestStruct {
   static void Test([Runtime::InteropServices::Out] String^ %s) {
      s = "a string";
   }
};
```

## <a name="example"></a>Örnek

Bu, önceki C# örnekte oluşturulan görsel C++ bileşeni tüketen bir istemcidir.

```
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

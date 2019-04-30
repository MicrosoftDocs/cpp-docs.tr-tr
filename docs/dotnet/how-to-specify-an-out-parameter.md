---
title: 'Nasıl yapılır: Belirttiğiniz bir parametre'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
ms.openlocfilehash: 901257b92aaa5e13e6e79d612ca590b734e15881
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387233"
---
# <a name="how-to-specify-an-out-parameter"></a>Nasıl yapılır: Belirttiğiniz bir parametre

Bu örnek, bir işlev parametresinin bir out parametresi olduğunu belirtmek nasıl ve bir C# programı bu işlevi çağırmak nasıl gösterir.

Visual C++ ile out parametresi belirtildiğinden <xref:System.Runtime.InteropServices.OutAttribute> .

## <a name="example"></a>Örnek

Bu örnekte ilk bölümünü out parametresi olan bir işlev içeren bir türe sahip bir Visual C++ DLL'ye ' dir.

```
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

Önceki örnekte oluşturulan Visual C++ bileşeni kullanan bir C# istemci budur.

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

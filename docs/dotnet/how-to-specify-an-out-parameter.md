---
title: 'Nasıl yapılır: belirttiğiniz bir parametre | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3af9c1d10206e89b0ad8462bd95fdf3b6062d713
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419509"
---
# <a name="how-to-specify-an-out-parameter"></a>Nasıl yapılır: Bir out Parametresini Belirleme

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

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
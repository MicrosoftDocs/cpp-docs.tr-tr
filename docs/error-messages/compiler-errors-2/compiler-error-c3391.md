---
title: Derleyici Hatası C3391
ms.date: 11/04/2016
f1_keywords:
- C3391
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
ms.openlocfilehash: cac397e4588c493fb8c47932feb97a5f12cf2583
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578223"
---
# <a name="compiler-error-c3391"></a>Derleyici Hatası C3391

'type_arg': 'generic_type' genel ' param' genel parametresi için geçersiz tür bağımsız değişkeni, NULL olmayan bir değer türü olmalıdır

Genel tür yanlış örneği. Tür tanımını denetleyin. Daha fazla bilgi için <xref:System.Nullable> ve [genel türler](../../windows/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C# kullanan C + genel türleri yazılırken desteklenmeyen bazı kısıtlamalar içeren bir genel tür içeren bir bileşen oluşturmak için +/ CLI. Daha fazla bilgi için [tür parametrelerindeki kısıtlamalar](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```cs
// C3391.cs
// Compile by using: csc /target:library C3391.cs
// a C# program
public class GR<N>
where N : struct {}
```

Aşağıdaki örnek, C3391.dll bileşen kullanılabilir duruma geldiğinde C3391 oluşturur.

```cpp
// C3391_b.cpp
// Compile by using: cl /clr C3391_b.cpp
#using <C3391.dll>
using namespace System;
value class VClass {};

int main() {
   GR< Nullable<VClass> >^ a =
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK
}
```
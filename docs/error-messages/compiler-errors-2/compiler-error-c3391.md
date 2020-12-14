---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3391'
title: Derleyici hatası C3391
ms.date: 11/04/2016
f1_keywords:
- C3391
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
ms.openlocfilehash: 1bac535136b2c6115bf0f5ff31c9e098407e03bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313404"
---
# <a name="compiler-error-c3391"></a>Derleyici hatası C3391

' type_arg ': genel ' generic_type ' öğesinin ' param ' genel parametresi için geçersiz tür bağımsız değişkeni, null olamayan bir değer türü olmalıdır

Genel bir tür yanlış bir şekilde başlatıldı. Tür tanımını denetleyin. Daha fazla bilgi için bkz <xref:System.Nullable> . ve [Genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C# ' ta genel türler yazarken desteklenmeyen belirli kısıtlamalara sahip genel bir tür içeren bir bileşen oluşturmak Için C# kullanır. Daha fazla bilgi için bkz. [tür parametrelerindeki kısıtlamalar](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```csharp
// C3391.cs
// Compile by using: csc /target:library C3391.cs
// a C# program
public class GR<N>
where N : struct {}
```

C3391.dll bileşeni kullanılabilir olduğunda aşağıdaki örnek C3391 oluşturur.

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

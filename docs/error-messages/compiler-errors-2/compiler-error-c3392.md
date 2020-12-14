---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3392'
title: Derleyici hatası C3392
ms.date: 11/04/2016
f1_keywords:
- C3392
helpviewer_keywords:
- C3392
ms.assetid: e4757596-e2aa-4314-b01e-5c4bfd2110e9
ms.openlocfilehash: c64b49bee05079fd2d1b468d807af5b1fd89ba26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316342"
---
# <a name="compiler-error-c3392"></a>Derleyici hatası C3392

' type_arg ': genel ' generic_type ' öğesinin ' param ' genel parametresi için geçersiz tür bağımsız değişkeni, genel parametresiz bir oluşturucuya sahip olmalıdır

Genel bir tür yanlış bir şekilde başlatıldı. Tür tanımını denetleyin. Daha fazla bilgi için bkz.  [Genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C# ' ta genel türler yazarken desteklenmeyen belirli kısıtlamalara sahip genel bir tür içeren bir bileşen oluşturmak Için C# kullanır. Daha fazla bilgi için bkz. [tür parametrelerindeki kısıtlamalar](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```csharp
// C3392.cs
// Compile by using: csc /target:library C3392.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

C3392.dll bileşeni kullanılabilir olduğunda aşağıdaki örnek C3392 oluşturur.

```cpp
// C3392_b.cpp
// Compile by using: cl /clr C3392_b.cpp
#using <C3392.dll>

ref class R { R(int) {} };
ref class N { N() {} };

value class V {};

ref class N2 { public: N2() {} };
ref class R2 { public: R2() {} };

int main () {
   GR<R^, V, N^>^ gr1;   // C3392
   GR<R^, V, N2^>^ gr1a; // OK

   GR<R^, N^, N^>^ gr3;  // C3392
   GR<R^, V, N2^>^ gr3a; // OK

   GR<R^, V, R^>^ gr4;   // C3392
   GR<R^, V, R2^>^ gr4a; // OK
}
```

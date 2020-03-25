---
title: Derleyici hatası C3390
ms.date: 11/04/2016
f1_keywords:
- C3390
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
ms.openlocfilehash: 4c0544df55fc71ace697d7e0a53ba303706e1378
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201129"
---
# <a name="compiler-error-c3390"></a>Derleyici hatası C3390

' type_arg ': genel ' generic_type ' öğesinin ' param ' genel parametresi için geçersiz tür bağımsız değişkeni, bir başvuru türü olmalıdır

Genel bir tür yanlış bir şekilde başlatıldı.  Tür tanımını denetleyin.  Daha fazla bilgi için bkz. [Genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

İlk örnek,/Clriçinde C# C++genel türler yazarken desteklenmeyen belirli kısıtlamalara sahip genel bir tür içeren bir bileşen oluşturmak için kullanır. Daha fazla bilgi için bkz. [tür parametrelerindeki kısıtlamalar](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```csharp
// C3390.cs
// Compile by using: csc /target:library C3390.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

C3390. dll bileşeni kullanılabilir olduğunda, aşağıdaki örnek C3390 oluşturur.

```cpp
// C3390_b.cpp
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>
ref class R { R(int) {} };
value class V {};
ref struct N { N() {} };

int main () {
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type
   GR<R^, V, N^>^ gr2b; // OK
}
```

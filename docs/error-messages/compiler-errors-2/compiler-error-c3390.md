---
title: Derleyici Hatası C3390
ms.date: 11/04/2016
f1_keywords:
- C3390
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
ms.openlocfilehash: 3f1149d4584a0ea3d0061a3ec4e2b77830603ef2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400324"
---
# <a name="compiler-error-c3390"></a>Derleyici Hatası C3390

'type_arg': 'generic_type' genel ' param' genel parametresi için geçersiz tür bağımsız değişkeni bir başvuru türü olmalıdır

Genel tür yanlış örneği.  Tür tanımını denetleyin.  Daha fazla bilgi için [genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

İlk örnek C# kullanan C + genel türleri yazılırken desteklenmeyen bazı kısıtlamalar içeren bir genel tür içeren bir bileşen oluşturmak için +/ CLR. Daha fazla bilgi için [tür parametrelerindeki kısıtlamalar](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```cs
// C3390.cs
// Compile by using: csc /target:library C3390.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

Aşağıdaki örnek, C3390.dll bileşen kullanılabilir duruma geldiğinde C3390 oluşturur.

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
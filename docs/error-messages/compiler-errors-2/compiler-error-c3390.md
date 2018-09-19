---
title: Derleyici Hatası C3390 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3390
dev_langs:
- C++
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7f1a19d86e133d01a17703f7ef4b3a79d5eb601
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111998"
---
# <a name="compiler-error-c3390"></a>Derleyici Hatası C3390

'type_arg': 'generic_type' genel ' param' genel parametresi için geçersiz tür bağımsız değişkeni bir başvuru türü olmalıdır

Genel tür yanlış örneği.  Tür tanımını denetleyin.  Daha fazla bilgi için [genel türler](../../windows/generics-cpp-component-extensions.md).

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
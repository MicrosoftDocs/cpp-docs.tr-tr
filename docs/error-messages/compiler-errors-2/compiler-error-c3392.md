---
title: Derleyici Hatası C3392 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3392
dev_langs:
- C++
helpviewer_keywords:
- C3392
ms.assetid: e4757596-e2aa-4314-b01e-5c4bfd2110e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04c69220cf9b6bf10a6bae8f9557f83d1e004752
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112817"
---
# <a name="compiler-error-c3392"></a>Derleyici Hatası C3392

'type_arg': 'generic_type' genel ' param' genel parametresi için geçersiz tür bağımsız değişkeni, genel bir parametresiz oluşturucusu olmalıdır

Genel tür yanlış örneği. Tür tanımını denetleyin. Daha fazla bilgi için [genel türler](../../windows/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C# kullanan C + genel türleri yazılırken desteklenmeyen bazı kısıtlamalar içeren bir genel tür içeren bir bileşen oluşturmak için +/ CLI. Daha fazla bilgi için [tür parametrelerindeki kısıtlamalar](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```cs
// C3392.cs
// Compile by using: csc /target:library C3392.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

Aşağıdaki örnek, C3392.dll bileşen kullanılabilir duruma geldiğinde C3392 oluşturur.

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
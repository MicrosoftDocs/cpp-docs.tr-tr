---
title: Derleyici Uyarısı (düzey 1) C4383
ms.date: 11/04/2016
f1_keywords:
- C4383
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
ms.openlocfilehash: 2510dda59047632e2a4823f734feeffd0c0a5b02
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778045"
---
# <a name="compiler-warning-level-1-c4383"></a>Derleyici Uyarısı (düzey 1) C4383

'instance_dereference_operator': bir kullanıcı tanımlı 'operator' işleci olduğunda; müşteri başvurusunu değiştirmenin anlamı değiştirebilirsiniz işleci, işlenenin hakkında açık olmaya statik işlev olarak yazma

İçinde yönetilen bir türe başvuru işleci bir kullanıcı tanımlı örneği geçersiz kılma eklediğinizde, türün başvuru işleci yeteneğini tutamacın nesneyi döndürmek için potansiyel olarak geçersiz kılın. Göz önünde bulundurun, kullanıcı tarafından tanımlanan statik yazma başvuru kaldırma işleci.

Daha fazla bilgi için [işlemek nesne işleci (^)](../../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) ve [Tracking Reference Operator](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

Ayrıca, bir örnek işleci başvurulan meta verileri üzerinden diğer dil derleyicileri için kullanılabilir değil. Daha fazla bilgi için [kullanıcı tanımlı işleçler (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4383 oluşturur.

```
// C4383.cpp
// compile with: /clr /W1

ref struct S {
   int operator*() { return 0; }   // C4383
};

ref struct T {
   static int operator*(T%) { return 0; }
};

int main() {
   S s;
   S^ pS = %s;

   T t;
   T^ pT = %t;
   T% rT = *pT;
}
```
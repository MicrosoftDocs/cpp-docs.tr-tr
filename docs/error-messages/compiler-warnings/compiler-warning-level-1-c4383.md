---
title: Derleyici Uyarısı (düzey 1) C4383 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4383
dev_langs:
- C++
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e4ac56b4f94ee6ff7e6ade01dfadca0c00a92db
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094852"
---
# <a name="compiler-warning-level-1-c4383"></a>Derleyici Uyarısı (düzey 1) C4383

'instance_dereference_operator': bir kullanıcı tanımlı 'operator' işleci olduğunda; müşteri başvurusunu değiştirmenin anlamı değiştirebilirsiniz işleci, işlenenin hakkında açık olmaya statik işlev olarak yazma

İçinde yönetilen bir türe başvuru işleci bir kullanıcı tanımlı örneği geçersiz kılma eklediğinizde, türün başvuru işleci yeteneğini tutamacın nesneyi döndürmek için potansiyel olarak geçersiz kılın. Göz önünde bulundurun, kullanıcı tarafından tanımlanan statik yazma başvuru kaldırma işleci.

Daha fazla bilgi için [işlemek nesne işleci (^)](../../windows/handle-to-object-operator-hat-cpp-component-extensions.md) ve [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md).

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
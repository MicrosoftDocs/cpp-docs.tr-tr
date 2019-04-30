---
title: Derleyici Uyarısı (düzey 1) C4020
ms.date: 11/04/2016
f1_keywords:
- C4020
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
ms.openlocfilehash: 75148c210ddd2a611061d58c036d12c084f442cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400057"
---
# <a name="compiler-warning-level-1-c4020"></a>Derleyici Uyarısı (düzey 1) C4020

'function': Gerçek parametre sayısı fazla

Bir işlev çağrısındaki gerçek parametre sayısı işlev prototipi veya tanımı biçimsel parametre sayısını aşıyor. Derleyici, fazladan gerçek parametre çağırma işlevinin göre geçirir.

Aşağıdaki örnek, C4020 oluşturur:

```
// C4020.c
// compile with: /W1 /c
void f(int);
int main() {
   f(1,2);   // C4020
}
```

Olası çözüm:

```
// C4020b.c
// compile with: /c
void f(int);
int main() {
   f(1);
}
```
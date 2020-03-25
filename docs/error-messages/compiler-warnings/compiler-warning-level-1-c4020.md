---
title: Derleyici Uyarısı (düzey 1) C4020
ms.date: 11/04/2016
f1_keywords:
- C4020
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
ms.openlocfilehash: 2136e94a261b2f767165e43acfd66583e8d15e9f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164592"
---
# <a name="compiler-warning-level-1-c4020"></a>Derleyici Uyarısı (düzey 1) C4020

' function ': çok fazla sayıda gerçek parametre

Bir işlev çağrısındaki gerçek parametrelerin sayısı, işlev prototipi veya tanımındaki biçimsel parametre sayısını aşıyor. Derleyici, fazladan gerçek parametreleri işlevin çağırma kuralına göre geçirir.

Aşağıdaki örnek C4020 oluşturur:

```c
// C4020.c
// compile with: /W1 /c
void f(int);
int main() {
   f(1,2);   // C4020
}
```

Olası çözüm:

```c
// C4020b.c
// compile with: /c
void f(int);
int main() {
   f(1);
}
```

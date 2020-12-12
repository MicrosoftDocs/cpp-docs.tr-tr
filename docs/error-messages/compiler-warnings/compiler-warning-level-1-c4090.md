---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4090'
title: Derleyici Uyarısı (düzey 1) C4090
ms.date: 11/04/2016
f1_keywords:
- C4090
helpviewer_keywords:
- C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
ms.openlocfilehash: c096a32e5aa0d632d43d9990f3256c3f865bf796
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278109"
---
# <a name="compiler-warning-level-1-c4090"></a>Derleyici Uyarısı (düzey 1) C4090

' Operation ': farklı ' Modifier ' niteleyicileri

Bir işlemde kullanılan değişken, derleyicinin algılanmadan değiştirilmesini engelleyen belirtilen değiştirici ile tanımlanır. İfade değişiklik yapılmadan derlenir.

Ya da **`const`** öğesine işaret olarak bildirilmemiş bir işaretçiye veya öğesine işaretçi atandığında bu uyarı oluşabilir **`volatile`** **`const`** **`volatile`** .

Bu uyarı C programları için verilir. C++ programında, derleyici bir hata verir: [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md).

Aşağıdaki örnek C4090 oluşturur:

```c
// C4090.c
// compile with: /W1
int *volatile *p;
int *const *q;
int **r;

int main() {
   p = q;   // C4090
   p = r;
   q = p;   // C4090
   q = r;
   r = p;   // C4090
   r = q;   // C4090
}
```

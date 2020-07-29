---
title: Derleyici Uyarısı (düzey 1) C4090
ms.date: 11/04/2016
f1_keywords:
- C4090
helpviewer_keywords:
- C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
ms.openlocfilehash: c4cb71355b4f3dca66c56ed4b89012ca9b9e646d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87197052"
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

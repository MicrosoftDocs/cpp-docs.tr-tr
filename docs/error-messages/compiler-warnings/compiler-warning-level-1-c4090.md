---
title: Derleyici Uyarısı (düzey 1) C4090
ms.date: 11/04/2016
f1_keywords:
- C4090
helpviewer_keywords:
- C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
ms.openlocfilehash: 88ed48e9bf7057c55ee4004ca1bb1eb18cd4be51
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626159"
---
# <a name="compiler-warning-level-1-c4090"></a>Derleyici Uyarısı (düzey 1) C4090

' Operation ': farklı ' Modifier ' niteleyicileri

Bir işlemde kullanılan değişken, derleyicinin algılanmadan değiştirilmesini engelleyen belirtilen değiştirici ile tanımlanır. İfade değişiklik yapılmadan derlenir.

**Const veya** `volatile` öğesine yönelik bir işaretçi **const** veya `volatile`işaret olarak bildirilmemiş bir işaretçiye atandığında bu uyarıya neden olabilir.

Bu uyarı C programları için verilir. Bir C++ programda derleyici bir hata verir: [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md).

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
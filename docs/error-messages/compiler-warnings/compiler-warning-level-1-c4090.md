---
title: Derleyici Uyarısı (düzey 1) C4090
ms.date: 11/04/2016
f1_keywords:
- C4090
helpviewer_keywords:
- C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
ms.openlocfilehash: b47d0bfbb6eab24fbe811d3e4f79b6bd86b3bb11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462380"
---
# <a name="compiler-warning-level-1-c4090"></a>Derleyici Uyarısı (düzey 1) C4090

'operation': farklı 'değiştiricisi' niteleyicileri

Bir işlemde kullanılan bir değişken algılama derleyici tarafından değiştirilmesi önlenir belirtilen bir değiştiricisi ile tanımlanır. İfade, hiçbir değişikliğe gerek olmadan derlenir.

Bu uyarı için bir işaretçi olmasından kaynaklanabilir bir **const** veya `volatile` öğesi bir işaretçiye işaret olarak bildirilmedi atandığı **const** veya `volatile`.

Bu uyarı, C programları için görüntülenir. C++ programında, derleyici bir hata verir: [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md).

Aşağıdaki örnek, C4090 oluşturur:

```
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
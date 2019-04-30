---
title: Derleyici Hatası C2208
ms.date: 11/04/2016
f1_keywords:
- C2208
helpviewer_keywords:
- C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
ms.openlocfilehash: 7970ba5d8d2b19bd6e330fad1879880fc5cbf32d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400454"
---
# <a name="compiler-error-c2208"></a>Derleyici Hatası C2208

'type': Bu tür kullanılarak tanımlanmış bir üye yok

İçin bir tür adı çözülürken bir tanımlayıcı, bir toplama bildiriminde olmakla birlikte derleyici üyesi bildiremezsiniz.

Aşağıdaki örnek, C2208 oluşturur:

```
// C2208.cpp
class C {
   C;   // C2208
   C(){}   // OK
};
```
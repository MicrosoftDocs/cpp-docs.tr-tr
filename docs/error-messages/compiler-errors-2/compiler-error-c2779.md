---
title: Derleyici Hatası C2779
ms.date: 11/04/2016
f1_keywords:
- C2779
helpviewer_keywords:
- C2779
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
ms.openlocfilehash: 7cf8aed276ab2aea61dc92b9e9fcbff9552c2ad6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449328"
---
# <a name="compiler-error-c2779"></a>Derleyici Hatası C2779

'bildirim': özellik yöntemleri yalnızca statik olmayan veri üyeleriyle ilişkilendirilmiş olabilir

`property` Genişletilmiş öznitelik, bir statik veri üyesine yanlış uygulanır.

Aşağıdaki örnek, C2779 oluşturur:

```
// C2779.cpp
struct A {
   static __declspec(property(put=PutProp))
   // try the following line instead
   __declspec(property(put=PutProp))
      int prop;   // C2779
   int PutProp(void);
};
```
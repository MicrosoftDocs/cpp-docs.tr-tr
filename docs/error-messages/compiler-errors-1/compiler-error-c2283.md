---
title: Derleyici Hatası C2283
ms.date: 11/04/2016
f1_keywords:
- C2283
helpviewer_keywords:
- C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
ms.openlocfilehash: 1113236680241a80c462e382c8c9c7de342b5463
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630002"
---
# <a name="compiler-error-c2283"></a>Derleyici Hatası C2283

'identifier': Saf belirtici veya soyut geçersiz kılma belirticisi adsız yapı üzerinde izin verilmiyor

Bir üye işlevi bir adsız sınıf veya yapının, izin verilmeyen bir saf tanımlayıcı ile bildirilir.

Aşağıdaki örnek, C2283 oluşturur:

```
// C2283.cpp
// compile with: /c
struct {
   virtual void func() = 0;   // C2283
};
struct T {
   virtual void func() = 0;   // OK
};
```
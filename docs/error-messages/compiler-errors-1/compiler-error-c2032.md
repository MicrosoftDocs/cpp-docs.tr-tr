---
title: Derleyici Hatası C2032
ms.date: 11/04/2016
f1_keywords:
- C2032
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
ms.openlocfilehash: 5743aba880f23d7706940936fc4a3a1973a84ca1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558255"
---
# <a name="compiler-error-c2032"></a>Derleyici Hatası C2032

'identifier': işlev, yapı/birleşim 'structorunion' üyesi olamaz

Yapı veya birleşim c++ ancak c içinde izin verilen bir üye işlevi vardır. Hatayı gidermek için bir C++ programı olarak derleyin veya üye işlevi kaldırın.

Aşağıdaki örnek, C2032 oluşturur:

```
// C2032.c
struct z {
   int i;
   void func();   // C2032
};
```

Olası çözüm:

```
// C2032b.c
// compile with: /c
struct z {
   int i;
};
```
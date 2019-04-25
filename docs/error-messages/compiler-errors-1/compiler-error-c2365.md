---
title: Derleyici Hatası C2365
ms.date: 11/04/2016
f1_keywords:
- C2365
helpviewer_keywords:
- C2365
ms.assetid: 35839b0b-4055-4b79-8957-b3a0871bdd02
ms.openlocfilehash: 9d862fb06041b01c306560264758d13f8f75b491
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230379"
---
# <a name="compiler-error-c2365"></a>Derleyici Hatası C2365

'sınıf üyesi': yeniden tanımlama; Önceki tanım 'sınıf üyesi' belirtildi

Sınıf üyesi bulunabileceğini çalışıldı.

Aşağıdaki örnek, C2365 oluşturur.

```
// C2365.cpp
// compile with: /c
class C1 {
   int CFunc();
   char *CFunc;   // C2365, already exists as a member function

   int CMem;
   char *CMem();   // C2365, already exists as a data member
};
```
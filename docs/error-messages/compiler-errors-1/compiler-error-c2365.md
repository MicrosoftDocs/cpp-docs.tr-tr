---
title: Derleyici Hatası C2365 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2365
dev_langs:
- C++
helpviewer_keywords:
- C2365
ms.assetid: 35839b0b-4055-4b79-8957-b3a0871bdd02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8809c4137cd9b3c1d45960387b8a28bdb007ac8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029162"
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
---
title: Derleyici Hatası C2459
ms.date: 11/04/2016
f1_keywords:
- C2459
helpviewer_keywords:
- C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
ms.openlocfilehash: d2e8b375fd1219b11b3a543bf3a565ddee00ccf2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502070"
---
# <a name="compiler-error-c2459"></a>Derleyici Hatası C2459

'identifier': tanımlanıyor; bir anonim üye olarak eklenemez

Bir sınıf, yapı veya birleşim kendi kapsamı içinde anonim birleşim üyesi tarafından tanımlandı.

Aşağıdaki örnek, C2459 oluşturur:

```
// C2459.cpp
// compile with: /c
class C {
   union { int C; };   // C2459
   union { int D; };
};
```
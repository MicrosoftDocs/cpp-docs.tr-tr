---
title: Derleyici Hatası C2231
ms.date: 11/04/2016
f1_keywords:
- C2231
helpviewer_keywords:
- C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
ms.openlocfilehash: 0d6519bd12cdb5ee5a86fa4a6915b51b0dc59fc5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383314"
---
# <a name="compiler-error-c2231"></a>Derleyici Hatası C2231

'.': 'sınıf anahtarı için' işlenen noktaları sol, '->' kullanın

(.) Üye seçme işleminin sol işleneni, bir sınıf, yapı veya birleşim yerine bir işaretçisidir.

Aşağıdaki örnek, C2231 oluşturur:

```
// C2231.c
struct S {
   int member;
} s, *ps = &s;
int main() {
   ps.member = 0;   // C2231

   // OK
   ps->member = 0;   // crash
   s.member = 0;
}
```
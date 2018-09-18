---
title: Derleyici Hatası C2231 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2231
dev_langs:
- C++
helpviewer_keywords:
- C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd6cd35d20f4ce0377aa5ae5cd66cd8c08004fb8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021687"
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
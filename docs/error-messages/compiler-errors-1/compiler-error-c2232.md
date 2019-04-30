---
title: Derleyici Hatası C2232
ms.date: 11/04/2016
f1_keywords:
- C2232
helpviewer_keywords:
- C2232
ms.assetid: 76f302b7-30a7-4a81-9a39-b4edde33b54c
ms.openlocfilehash: f1478c2d06ab535a532b1be45c2db69050afe7b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376646"
---
# <a name="compiler-error-c2232"></a>Derleyici Hatası C2232

'->': sol işlenen '' kullanan sınıf anahtarı türüne sahip, '.'

İşlenen solundaki `->` işleci bir işaretçi değil. Bir sınıf, yapı veya birleşim nokta (.) işlecini kullanın.

Aşağıdaki örnek, C2232 oluşturur:

```
// C2232.c
struct X {
    int member;
} x, *px;
int main() {
    x->member = 0;   // C2232, x is not a pointer

    px->member = 0;
    x.member = 0;
}
```
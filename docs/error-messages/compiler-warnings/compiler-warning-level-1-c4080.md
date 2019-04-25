---
title: Derleyici Uyarısı (düzey 1) C4080
ms.date: 11/04/2016
f1_keywords:
- C4080
helpviewer_keywords:
- C4080
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
ms.openlocfilehash: a91963d524300c8768768a8a4615b1ab27e033e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256290"
---
# <a name="compiler-warning-level-1-c4080"></a>Derleyici Uyarısı (düzey 1) C4080

kesim adı için tanımlayıcı bekleniyordu; 'symbol' bulundu

Kesimdeki adını [#pragma alloc_text](../../preprocessor/alloc-text.md) bir dize veya bir tanımlayıcı olmalıdır. Geçerli bir tanımlayıcı bulunmazsa derleyici pragma yok sayar.

Aşağıdaki örnek, C4080 oluşturur:

```
// C4080.cpp
// compile with: /W1
extern "C" void func(void);

#pragma alloc_text()   // C4080

// try this line to resolve the warning
// #pragma alloc_text("mysection", func)

int main() {
}

void func(void) {
}
```
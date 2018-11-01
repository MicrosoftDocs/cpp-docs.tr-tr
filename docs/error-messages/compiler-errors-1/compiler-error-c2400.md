---
title: Derleyici Hatası C2400
ms.date: 11/04/2016
f1_keywords:
- C2400
helpviewer_keywords:
- C2400
ms.assetid: 1ba441ee-73f9-42a5-bfe9-fbeab93808eb
ms.openlocfilehash: 3ede43ec5ddb61b85c48094193d01d18bacae2bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667187"
---
# <a name="compiler-error-c2400"></a>Derleyici Hatası C2400

Satır içi assembler sözdizimi hatası 'bağlamında'; 'token' bulundu

Belirteç Belirtilen adda bir söz dizimi hatası neden oldu.

Aşağıdaki örnek, C2400 oluşturur:

```
// C2400.cpp
// processor: x86
int main() {
   __asm {
      heh ax,bx;   // C2400, heh is not a valid x86 instruction
      mov ax,bx;   // OK
   }
}
```
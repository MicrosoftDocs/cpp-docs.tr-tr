---
title: Derleyici hatası C2400
ms.date: 11/04/2016
f1_keywords:
- C2400
helpviewer_keywords:
- C2400
ms.assetid: 1ba441ee-73f9-42a5-bfe9-fbeab93808eb
ms.openlocfilehash: 61043f3f97d4d91b66c3902cc33ed4be526541ae
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744777"
---
# <a name="compiler-error-c2400"></a>Derleyici hatası C2400

' Context ' içinde satır içi assembler sözdizimi hatası; ' token ' bulundu

Belirteç belirtilen bağlamda bir sözdizimi hatasına neden oldu.

Aşağıdaki örnek C2400 oluşturur:

```cpp
// C2400.cpp
// processor: x86
int main() {
   __asm {
      heh ax,bx;   // C2400, heh is not a valid x86 instruction
      mov ax,bx;   // OK
   }
}
```

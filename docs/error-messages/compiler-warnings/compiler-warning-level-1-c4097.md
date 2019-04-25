---
title: Derleyici Uyarısı (düzey 1) C4097
ms.date: 11/04/2016
f1_keywords:
- C4097
helpviewer_keywords:
- C4097
ms.assetid: 2525be51-fac2-43b2-b57c-3bbf1a2268f7
ms.openlocfilehash: d27e1d33db7a531d541bffdac015176de72077d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152204"
---
# <a name="compiler-warning-level-1-c4097"></a>Derleyici Uyarısı (düzey 1) C4097

pragma parametresinin 'restore' olması bekleniyor veya 'off'

Pragma, geçersiz bir değer geçirildi.

Aşağıdaki örnek, C4097 oluşturur:

```
// C4097.cpp
// compile with: /W1
#pragma runtime_checks("",test)   // C4097
// try the following line instead
// #pragma runtime_checks("",off)

int main() {
}
```
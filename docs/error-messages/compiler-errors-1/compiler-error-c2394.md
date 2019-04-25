---
title: Derleyici Hatası C2394
ms.date: 11/04/2016
f1_keywords:
- C2394
helpviewer_keywords:
- C2394
ms.assetid: 653fa9a0-29b3-48aa-bc01-82f98f717a2b
ms.openlocfilehash: a18b09bcb5e6f4e743a8b1668cd0057b02a60a8a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303703"
---
# <a name="compiler-error-c2394"></a>Derleyici Hatası C2394

'your_type::operator'op' ": CLR veya WinRToperator geçerli değil. En az bir parametre aşağıdaki türlerde olmalıdır: 'T ^', 'T ^ %', 'T ^ &', burada T = 'your_type'

Bir Windows çalışma zamanı veya yönetilen türü bir işleç türü işleç dönüş değerinin türü ile aynı olan en az bir parametre yok.

Aşağıdaki örnek, C2394 oluşturur:

```
// C2394.cpp
// compile with: /clr /c
ref struct Y {
   static Y^ operator -(int i, char c);   // C2394

   // OK
   static Y^ operator -(Y^ hY, char c);
   // or
   static Y^ operator -(int i, Y^& rhY);
};
```
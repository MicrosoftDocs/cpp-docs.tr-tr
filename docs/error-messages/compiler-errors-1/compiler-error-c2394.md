---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2394'
title: Derleyici hatası C2394
ms.date: 11/04/2016
f1_keywords:
- C2394
helpviewer_keywords:
- C2394
ms.assetid: 653fa9a0-29b3-48aa-bc01-82f98f717a2b
ms.openlocfilehash: 116ab480c5a72c18bfa551e582fb797d3c216d6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194883"
---
# <a name="compiler-error-c2394"></a>Derleyici hatası C2394

' your_type:: operator'op ' ": CLR veya WinRToperator geçerli değil. En az bir parametre şu türlerde olmalıdır: 'T ^ ', 'T ^% ', 'T ^& ', burada T = ' your_type '

Windows Çalışma Zamanı veya yönetilen türdeki bir operatör, türü işleç dönüş değerinin türüyle aynı olan en az bir parametreye sahip değildi.

Aşağıdaki örnek C2394 oluşturur:

```cpp
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

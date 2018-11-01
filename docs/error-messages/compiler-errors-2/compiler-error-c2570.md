---
title: Derleyici Hatası C2570
ms.date: 11/04/2016
f1_keywords:
- C2570
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
ms.openlocfilehash: 447869b029df41219f71dcc633e9ae8a3934e0ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549584"
---
# <a name="compiler-error-c2570"></a>Derleyici Hatası C2570

'identifier': birleşimin taban sınıfları olamaz

UNION, sınıf, yapı veya birleşim türetilir. Buna izin verilmez. Türetilmiş bir tür bir sınıf veya yapı bunun yerine bildirin.

Aşağıdaki örnek C2570 oluşturur:

```
// C2570.cpp
// compile with: /c
class base {};
union hasPubBase : public base {};   // C2570
union hasNoBase {};   // OK
```
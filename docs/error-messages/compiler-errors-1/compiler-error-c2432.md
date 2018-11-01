---
title: Derleyici Hatası C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: e2983d966a6290ce19713c63feb502c8ffc74bf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631258"
---
# <a name="compiler-error-c2432"></a>Derleyici Hatası C2432

'identifier' içinde 16-bit verilere geçersiz başvuru

Bir 16-bit kayıt temel kaydettirmeye veya bir dizin kullanılır. Derleyici, 16-bit verilere başvurma desteklemez. 16-bit kayıtlarını dizini veya temel kasa için 32-bit kod derlenirken kullanılamaz.

Aşağıdaki örnek, C2432 oluşturur:

```
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```
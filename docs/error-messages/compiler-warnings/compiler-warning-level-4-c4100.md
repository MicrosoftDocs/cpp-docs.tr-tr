---
title: Derleyici Uyarısı (düzey 4) C4100
ms.date: 11/04/2016
f1_keywords:
- C4100
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
ms.openlocfilehash: ccb438cf7c80edb1403683ac4817617ffccc690d
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447737"
---
# <a name="compiler-warning-level-4-c4100"></a>Derleyici Uyarısı (düzey 4) C4100

'identifier': başvurulmayan biçimsel parametre

Biçimsel parametre işlevin gövdesinde başvurulmuyor. Başvurulmayan parametre yok sayıldı.

C4100, ayrıca kod bir yok edici çağırdığında verilebilir bir başvurulmayan parametresinde ilkel türü.  Bu bir sınırlamadır Microsoft C++ derleyici.

Şu örnek C4100 oluşturur:

```
// C4100.cpp
// compile with: /W4
void func(int i) {   // C4100, delete the unreferenced parameter to
                     //resolve the warning
   // i;   // or, add a reference like this
}

int main()
{
   func(1);
}
```
---
title: Derleyici Hatası C2428
ms.date: 11/04/2016
f1_keywords:
- C2428
helpviewer_keywords:
- C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
ms.openlocfilehash: 299a4e899a41bf47eec5eaf5b54d2307e557078e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165833"
---
# <a name="compiler-error-c2428"></a>Derleyici Hatası C2428

'operation': 'bool' türü işlenen üzerinde izin verilmiyor

Azaltma işleci türündeki nesnelere uygulayamazsınız `bool`.

Aşağıdaki örnek, C2428 oluşturur:

```
// C2428.cpp
void g(bool fFlag) {
   --fFlag;   // C2428
   fFlag--;   // C2428
}
```
---
title: Derleyici Hatası C2196
ms.date: 11/04/2016
f1_keywords:
- C2196
helpviewer_keywords:
- C2196
ms.assetid: fd2f6a58-48ce-4e58-96f8-e37720feb8e7
ms.openlocfilehash: f21652161cb654fa41562ff97b2a5b4741f51855
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174568"
---
# <a name="compiler-error-c2196"></a>Derleyici Hatası C2196

Case değeri 'value' önceden kullanıldı.

Switch deyimi birden çok kez aynı büyük/küçük harf değeri kullanır.

Aşağıdaki örnek, C2196 oluşturur:

```
// C2196.cpp
int main() {
   int i = 0;
   switch( i ) {
   case 0:
      break;
   case 0:   // C2196
   // try the following line instead
   // case 1:
      break;
   }
}
```
---
title: Derleyici Uyarısı (düzey 1) C4353
ms.date: 11/04/2016
f1_keywords:
- C4353
helpviewer_keywords:
- C4353
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
ms.openlocfilehash: 305c1156ae8dc664edba17287786db50bfabbd18
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384198"
---
# <a name="compiler-warning-level-1-c4353"></a>Derleyici Uyarısı (düzey 1) C4353

Standart olmayan uzantı kullanıldı: işlev ifadesi olarak 0 sabiti. Bunun yerine '__noop ' iç işlevini iç kullanın

İşlev ifadesi olarak sabit sıfır (0) kullanamazsınız. Daha fazla bilgi için [__noop](../../intrinsics/noop.md).

Aşağıdaki örnek, C4353 oluşturur:

```
// C4353.cpp
// compile with: /W1
void MyPrintf(void){};
#define X 0
#if X
   #define DBPRINT MyPrint
#else
   #define DBPRINT 0   // C4353 expected
#endif
int main(){
DBPRINT();
}
```
---
title: Derleyici Uyarısı (düzey 1) C4353
ms.date: 11/04/2016
f1_keywords:
- C4353
helpviewer_keywords:
- C4353
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
ms.openlocfilehash: 9c91a3d21a16cc8891d6f04db49c3a0f0ec26e2c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187199"
---
# <a name="compiler-warning-level-1-c4353"></a>Derleyici Uyarısı (düzey 1) C4353

Standart olmayan uzantı kullanıldı: işlev ifadesi olarak sabit 0. Bunun yerine ' __noop ' işlev iç kullanın

Sıfır (0) sabitini işlev ifadesi olarak kullanamazsınız. Daha fazla bilgi için bkz. [__noop](../../intrinsics/noop.md).

Aşağıdaki örnek C4353 oluşturur:

```cpp
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

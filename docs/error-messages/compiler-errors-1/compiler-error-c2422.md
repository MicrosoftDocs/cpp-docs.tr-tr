---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2422'
title: Derleyici hatası C2422
ms.date: 11/04/2016
f1_keywords:
- C2422
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
ms.openlocfilehash: 4fb35b7613e523c750d6c3f15a8071117edba46a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120249"
---
# <a name="compiler-error-c2422"></a>Derleyici hatası C2422

' Operand ' içinde geçersiz kesim geçersiz kılma

Satır içi derleme kodu yanlış bir işlenen üzerinde bir kesim geçersiz kılma işleci (iki nokta üst üste) kullanır.  Olası nedenler şunlardır:

- İşlecinden önceki yazmaç bir segment kaydı değildir.

- İşleçten önceki kayıt, işlenenden yalnızca yazmaç segmenti değil.

- Segment geçersiz kılma işleci bir yöneltme işleci (köşeli ayraç) içinde görünür.

- Segment geçersiz kılma işlecinden sonraki ifade, dolaysız bir işlenen veya bir bellek işleneni değil.

Aşağıdaki örnek C2422 oluşturur:

```cpp
// C2422.cpp
// processor: x86
int main() {
   _asm {
      mov AX, [BX:ES]   // C2422
      mov AX, ES   // OK
   }
}
```

---
title: Derleyici hatası C2422
ms.date: 11/04/2016
f1_keywords:
- C2422
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
ms.openlocfilehash: 39f779ee846cf4f328f9c7af59ae394d97d7a3ca
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744738"
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

---
title: Derleyici Hatası C2422
ms.date: 11/04/2016
f1_keywords:
- C2422
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
ms.openlocfilehash: 524eeadb6cf066d3eba3a7e88c45a9e2b993c0ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402898"
---
# <a name="compiler-error-c2422"></a>Derleyici Hatası C2422

'işleneni' içindeki kesim geçersiz kılma

Satır içi derleme kodu, yanlış bir işlenen üzerinde bir kesim geçersiz kılma işleci (virgül) kullanır.  Olası nedenler şunlardır:

- İşleç önceki kayıt bir segment kaydı değil.

- İşleç önceki kayıt işlenende segment kaydeder değil.

- Yöneltme işleci (köşeli ayraç) kesim geçersiz kılma işleci görünür.

- Kesim geçersiz kılma işleci aşağıdaki ifade, bir anlık işlenen ya da bir bellek işlenen değil.

Aşağıdaki örnek, C2422 oluşturur:

```
// C2422.cpp
// processor: x86
int main() {
   _asm {
      mov AX, [BX:ES]   // C2422
      mov AX, ES   // OK
   }
}
```
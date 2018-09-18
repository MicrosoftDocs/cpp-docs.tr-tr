---
title: Derleyici Hatası C2422 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 17421f2d4a7823c0e2fbb34a54a7c562223c798c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047037"
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
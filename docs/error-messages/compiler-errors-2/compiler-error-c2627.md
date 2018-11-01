---
title: Derleyici Hatası C2627
ms.date: 11/04/2016
f1_keywords:
- C2627
helpviewer_keywords:
- C2627
ms.assetid: 7fc6c5ac-c7c9-4f0b-ad52-f52252526458
ms.openlocfilehash: dc976a0c16d19d1fd2340676e43eb71903163aa5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659065"
---
# <a name="compiler-error-c2627"></a>Derleyici Hatası C2627

'function': üye işlev anonim birleşimde izin verilmiyor

Bir [anonim birleşim](../../cpp/unions.md#anonymous_unions) üye işlevleri sahip olamaz.

Aşağıdaki örnek, C2627 oluşturur:

```
// C2627.cpp
int main() {
   union { void f(){} };   // C2627
   union X { void f(){} };
}
```
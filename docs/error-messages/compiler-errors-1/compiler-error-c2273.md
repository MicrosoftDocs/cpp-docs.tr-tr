---
title: Derleyici Hatası C2273 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2273
dev_langs:
- C++
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 995f75487820976d045e5db05fe2b170260240cc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066225"
---
# <a name="compiler-error-c2273"></a>Derleyici Hatası C2273

'type': '->' işlecinin sağ tarafı olarak geçersizdir

Bir tür sağ işleneni görünür bir `->` işleci.

Bu hata, bir kullanıcı tanımlı tür dönüştürme erişmeye tarafından kaynaklanabilir. Anahtar sözcüğünü kullanın `operator` arasında -> ve `type`.

Aşağıdaki örnek, C2273 oluşturur:

```
// C2273.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};
int main() {
   MyClass * ClassPtr = new MyClass;
   int i = ClassPtr->int();   // C2273
   int j = ClassPtr-> operator int();   // OK
}
```
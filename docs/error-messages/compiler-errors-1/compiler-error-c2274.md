---
title: Derleyici Hatası C2274 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2274
dev_langs:
- C++
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fcc6b0afe78e089c268f69274be1cbfb6f3d32c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093215"
---
# <a name="compiler-error-c2274"></a>Derleyici Hatası C2274

'type': sağ tarafı olarak geçersizdir '.' işleci

Bir tür, üye erişimi (.) işlecinin sağ işlenen görünür.

Bu hata, bir kullanıcı tanımlı tür dönüştürme erişmeye tarafından kaynaklanabilir. Anahtar sözcüğünü kullanın `operator` dönem arasında ve `type`.

Aşağıdaki örnek, C2286 oluşturur:

```
// C2274.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};

int main() {
   MyClass ClassName;
   int i = ClassName.int();   // C2274
   int j = ClassName.operator int();   // OK
}
```
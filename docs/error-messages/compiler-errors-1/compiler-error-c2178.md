---
title: Derleyici Hatası C2178 | Microsoft Docs
ms.custom: ''
ms.date: 05/08/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2178
dev_langs:
- C++
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af9efdb3258e6793a17a26b552df8ba4e63c9107
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102345"
---
# <a name="compiler-error-c2178"></a>Derleyici Hatası C2178

'*tanımlayıcı*'ile bildirilemez'*belirticisi*' tanımlayıcısı

A `mutable` belirleyici bir bildirimde kullanıldı, ancak bu bağlamda belirticisine izin verilmiyor.

`mutable` Belirticisi yalnızca sınıf veri üyeleri adlarına uygulanan ve bildirilen adlar için uygulanamaz `const` veya `static`ve üyeleri başvurmak için uygulanamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl C2178 oluşabilir ve bu sorunun nasıl gösterir.

```
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```

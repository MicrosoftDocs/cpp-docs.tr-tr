---
title: Derleyici Hatası C2178
ms.date: 05/08/2017
f1_keywords:
- C2178
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
ms.openlocfilehash: cd153bb5b331872bfe35b046d41612998bd0eff7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386011"
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

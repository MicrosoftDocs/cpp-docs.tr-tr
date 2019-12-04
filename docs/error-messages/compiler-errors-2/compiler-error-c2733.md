---
title: Derleyici hatası C2733
ms.date: 11/04/2016
f1_keywords:
- C2733
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
ms.openlocfilehash: 3ef669a49f4a3ec5a1af1a15a79f2511fa2699dd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755791"
---
# <a name="compiler-error-c2733"></a>Derleyici hatası C2733

aşırı yüklenmiş ' function ' işlevinin ikinci C bağlantısına izin verilmiyor

Birden fazla aşırı yüklenmiş işlev C bağlantısıyla birlikte bildirilmiştir. C bağlantısı kullanılırken, belirtilen bir işlevin yalnızca bir biçimi dış olabilir. Aşırı yüklenmiş işlevler aynı adı taşıyan bir ada sahip olduğundan, C programlarıyla birlikte kullanılamaz.

Aşağıdaki örnek C2733 oluşturur:

```cpp
// C2733.cpp
extern "C" {
   void F1(int);
}

extern "C" {
   void F1();   // C2733
   // try the following line instead
   // void F2();
}
```

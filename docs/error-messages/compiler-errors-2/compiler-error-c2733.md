---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2733'
title: Derleyici hatası C2733
ms.date: 11/04/2016
f1_keywords:
- C2733
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
ms.openlocfilehash: f957be13b8c1de1ee3ada98ffd42f0d89fc7755c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123207"
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

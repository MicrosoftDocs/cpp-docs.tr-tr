---
title: Derleyici Hatası C2733
ms.date: 11/04/2016
f1_keywords:
- C2733
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
ms.openlocfilehash: 26819f1928223b5fa96d275290105f32787057f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208330"
---
# <a name="compiler-error-c2733"></a>Derleyici Hatası C2733

'function' izin aşırı yüklü işlevin ikinci C bağlaması

Birden fazla aşırı yüklenmiş işlev C bağlaması ile bildirilir. C bağlaması kullanırken, belirtilen işlevinin yalnızca bir form dış olabilir. Aşırı yüklenmiş işlevler ve aynı ada sahip olduğundan, C programları ile kullanılamaz.

Aşağıdaki örnek, C2733 oluşturur:

```
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
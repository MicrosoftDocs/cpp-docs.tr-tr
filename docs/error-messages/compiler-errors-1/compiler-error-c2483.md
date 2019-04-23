---
title: Derleyici Hatası C2483
ms.date: 09/15/2017
f1_keywords:
- C2483
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
ms.openlocfilehash: 7a627ce28e60f42dabcf0a257464a8bfbd58b9a4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028633"
---
# <a name="compiler-error-c2483"></a>Derleyici Hatası C2483

>'*tanımlayıcı*': 'thread' nesnesiyle oluşturucu veya yıkıcı bildirilemez

Visual Studio 2015 ve sonraki sürümlerinde, bu hata iletisi geçersiz. Önceki sürümlerde ile bildirilen değişkenlerin `thread` öznitelik, bir oluşturucu veya çalışma zamanı değerlendirme gerektiren diğer ifade ile başlatılamaz. Statik bir ifade başlatmak için gerekli `thread` veri.

## <a name="example"></a>Örnek

Aşağıdaki örnek, Visual Studio 2013 veya önceki sürümlerinde C2483 oluşturur.

```cpp
// C2483.cpp
// compile with: /c
__declspec(thread) struct A {
   A(){}
   ~A(){}
} aa;   // C2483 error

__declspec(thread) struct B {} b;   // OK
```

## <a name="see-also"></a>Ayrıca bkz.

[thread](../../cpp/thread.md)
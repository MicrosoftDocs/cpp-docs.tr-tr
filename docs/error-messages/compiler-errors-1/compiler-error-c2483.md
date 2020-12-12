---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2483'
title: Derleyici hatası C2483
ms.date: 09/15/2017
f1_keywords:
- C2483
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
ms.openlocfilehash: 5edafbbb0852eb622f34698421ce9a2b794f9209
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123883"
---
# <a name="compiler-error-c2483"></a>Derleyici hatası C2483

>'*tanımlayıcı*': oluşturucuya veya yıkıcıya sahip nesne ' Thread ' olarak bildirilemez

Bu hata iletisi, Visual Studio 2015 ve sonraki sürümlerinde artık kullanılmıyor. Önceki sürümlerde, özniteliğiyle tanımlanan değişkenler `thread` bir Oluşturucu veya çalışma zamanı değerlendirmesi gerektiren başka bir ifadeyle başlatılamaz. Verileri başlatmak için statik bir ifade gerekir `thread` .

## <a name="example"></a>Örnek

Aşağıdaki örnek, Visual Studio 2013 ve önceki sürümlerde C2483 oluşturur.

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

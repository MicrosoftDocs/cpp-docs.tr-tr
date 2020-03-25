---
title: Derleyici hatası C2483
ms.date: 09/15/2017
f1_keywords:
- C2483
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
ms.openlocfilehash: 20b08c0d2cd89224ed3d3b8b34915deb947b0b4b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205120"
---
# <a name="compiler-error-c2483"></a>Derleyici hatası C2483

>'*tanımlayıcı*': oluşturucuya veya yıkıcıya sahip nesne ' Thread ' olarak bildirilemez

Bu hata iletisi, Visual Studio 2015 ve sonraki sürümlerinde artık kullanılmıyor. Önceki sürümlerde `thread` özniteliğiyle belirtilen değişkenler, çalışma zamanı değerlendirmesi gerektiren bir Oluşturucu ya da başka bir ifadeyle başlatılamaz. `thread` verileri başlatmak için statik bir ifade gerekir.

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

---
title: "Derleyici Hatası C2483 | Microsoft Docs"
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2483
dev_langs:
- C++
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f7f9f30724c02d44e054bf16ff1460370c30e06
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2483"></a>Derleyici Hatası C2483

>'*tanımlayıcısı*': 'iş parçacığı' Oluşturucusu veya yıkıcı nesnesiyle bildirilemez

Bu hata iletisini Visual Studio 2015 ve sonraki sürümlerde kullanımdan kalkmıştır. Önceki sürümlerde ile değişkenleri bildirilen `thread` oluşturucu veya çalışma zamanı değerlendirme gerektiren diğer ifade özniteliği başlatılamıyor. Statik bir ifade başlatmak için gerekli `thread` veri.

## <a name="example"></a>Örnek

Aşağıdaki örnek, Visual Studio 2013 ve önceki sürümlerinde C2483 oluşturur.

```cpp
// C2483.cpp
// compile with: /c
__declspec(thread) struct A {
   A(){}
   ~A(){}
} aa;   // C2483 error  

__declspec(thread) struct B {} b;   // OK
```

## <a name="see-also"></a>Ayrıca Bkz.

[thread](../../cpp/thread.md)
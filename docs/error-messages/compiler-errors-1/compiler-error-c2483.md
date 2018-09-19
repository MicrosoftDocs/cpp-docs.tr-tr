---
title: Derleyici Hatası C2483 | Microsoft Docs
ms.custom: ''
ms.date: 09/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2483
dev_langs:
- C++
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be2a2caef9e1252bf1ab36253a7f5f715b94d5a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031619"
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

## <a name="see-also"></a>Ayrıca Bkz.

[thread](../../cpp/thread.md)
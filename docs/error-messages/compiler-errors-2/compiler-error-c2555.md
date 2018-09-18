---
title: Derleyici Hatası C2555 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2555
dev_langs:
- C++
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f91ec33db2d3a7b6772556233a3c99b501ede76
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017345"
---
# <a name="compiler-error-c2555"></a>Derleyici Hatası C2555

'class1::function1': geçersiz kılan sanal işlev dönüş türü farklıdır ve 'class2::function2' bunun bir kovaryansı değil

Bir sanal işlev ve türetilmiş bir geçersiz kılma işlevini aynı parametre listelerini ancak farklı dönüş türlerine sahip. Türetilen bir sınıfta geçersiz kılan bir işlev dönüş türü tarafından yalnızca bir temel sınıf sanal bir işlevi farklı olamaz.

Bu hatayı gidermek için sanal işlev çağrıldıktan sonra dönüş değeri dönüştürün.

/ CLR ile derleme yaparsanız, bu hatayı görebilirsiniz.   Örneğin, Visual C++ aşağıdaki C# bildirimine eşdeğer:

```
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

is

```
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];
```

Bilgi Bankası makalesi Q240862 C2555 hakkında daha fazla bilgi için bkz.

Aşağıdaki örnek, C2555 oluşturur:

```
// C2555.cpp
// compile with: /c
struct X {
   virtual void func();
};
struct Y : X {
   char func();  // C2555
   void func2();   // OK
};
```
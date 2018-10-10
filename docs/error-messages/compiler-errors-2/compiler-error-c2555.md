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
ms.openlocfilehash: b0cd401aa1ee3611befb39d630f48f6aed36211c
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48889952"
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

Aşağıdaki örnek, C2555 oluşturur:

```cpp
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
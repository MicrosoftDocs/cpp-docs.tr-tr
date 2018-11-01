---
title: Derleyici Hatası C2555
ms.date: 11/04/2016
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: cc6c3a3a29665ccf65b77a3d9866986cb0a46b9e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528862"
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
---
title: Derleyici hatası C2555
ms.date: 11/04/2016
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: ebf3e4a3aff48311edd5fb95b01a7b2d23990231
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202430"
---
# <a name="compiler-error-c2555"></a>Derleyici hatası C2555

' Class1:: işlev1 ': geçersiz kılan sanal işlev dönüş türü farklı ve ' Class2:: function2 ' öğesinden birlikte değişken değil

Sanal bir işlev ve türetilmiş geçersiz kılma işlevi özdeş parametre listelerine sahip ancak farklı dönüş türlerine sahip. Türetilmiş bir sınıftaki geçersiz kılma işlevi, bir temel sınıftaki sanal işlevden yalnızca dönüş türüne göre farklı olamaz.

Bu hatayı çözmek için, sanal işlev çağrıldıktan sonra dönüş değerini atayın.

Ayrıca,/clrile derlerseniz bu hatayı görebilirsiniz.   Örneğin, görsel C++ aşağıdaki C# bildirime eşdeğerdir:

```
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

is

```
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];
```

Aşağıdaki örnek C2555 oluşturur:

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

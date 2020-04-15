---
title: Derleyici Hatası C2555
description: Visual Studio C++ derleyici hatası C2555 için başvuru.
ms.date: 03/30/2020
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: fe0e6379e783387506e6098c9b14a047baa8e6c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374181"
---
# <a name="compiler-error-c2555"></a>Derleyici Hatası C2555

> '*class1*::*function1*': geçersiz kılan sanal işlev dönüş türü farklıdır ve '*class2*':*function2*' den eşdeğişken değildir

Sanal işlev ve türetilmiş geçersiz kılma işlevi aynı parametre listelerine ancak farklı iade türlerine sahiptir.

## <a name="remarks"></a>Açıklamalar

C++'da, türetilmiş bir sınıftaki geçersiz kılma işlevi yalnızca taban sınıftaki sanal işlevden gelen dönüş türüne göre farklı olamaz.

Belirli iade türleri için bu kuralın bir istisnası vardır. Türemiş bir sınıf ortak taban sınıfGeçersiz olduğunda, bir taban sınıf işaretçisi veya başvuru yerine türemiş sınıfa bir işaretçi veya başvuru döndürebilir. Bu dönüş *türleri,* türle birlikte değiştiğinden, birlikte varyant olarak adlandırılır. Bu kural özel durumu, ortak başvuru-işaretçi veya işaretçi-işaretçi türleri izin vermez.

Hatayı çözmenin bir yolu, taban sınıfla aynı türü döndürmektir. Ardından, sanal işlev çağrıldıktan sonra geri dönüş değerini atın. Başka bir da parametre listesini değiştirmek için, türemiş sınıf üye işlevi bir geçersiz kılma yerine aşırı yük yapmaktır.

## <a name="examples"></a>Örnekler

Bu hatayı derlerseniz **`/clr`** görebilirsiniz. Örneğin, C++ aşağıdaki C# bildirimine eşdeğerdir:

```csharp
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

is

```cpp
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

Düzeltmek için, return türünü `Y::func` ' `void`den ' olarak değiştirin.

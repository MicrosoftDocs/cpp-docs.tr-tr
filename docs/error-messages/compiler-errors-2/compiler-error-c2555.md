---
title: Derleyici hatası C2555
description: Visual Studio C++ derleyicisi hatası C2555 için başvuru.
ms.date: 03/30/2020
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: ecac92bc663a6344e9ddafe13c194a92ab944c51
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207803"
---
# <a name="compiler-error-c2555"></a>Derleyici hatası C2555

> '*Class1*::*işlev1*': geçersiz kılan sanal işlev dönüş türü farklı ve '*Class2*::*function2*' öğesinden birlikte değişken değil

Sanal bir işlev ve türetilmiş geçersiz kılma işlevi özdeş parametre listelerine sahip ancak farklı dönüş türlerine sahip.

## <a name="remarks"></a>Açıklamalar

C++ ' da, türetilmiş bir sınıftaki geçersiz kılma işlevi yalnızca temel sınıftaki bir sanal işlevden dönüş türü ile farklı olamaz.

Bu kural için belirli dönüş türleri için bir özel durum vardır. Türetilmiş bir sınıf ortak bir temel sınıfı geçersiz kıldığında, temel sınıf işaretçisi veya başvurusu yerine türetilmiş sınıfa bir işaretçi veya başvuru döndürebilir. Bu dönüş türleri, türle birlikte farklı olduklarından, birlikte *değişken*olarak adlandırılır. Bu kural özel durumu, birlikte değişken başvuruya işaretçiye veya işaretçiden işaretçiye türlere izin vermez.

Hatayı çözmek için bir yol, temel sınıfla aynı türü döndürmemelidir. Sonra, sanal işlev çağrıldıktan sonra dönüş değerini atayın. Başka bir deyişle, bir geçersiz kılma yerine türetilmiş sınıf üye işlevini aşırı yükleme yapmak için de parametre listesini de değiştirmek gerekir.

## <a name="examples"></a>Örnekler

İle derlerseniz bu hatayı görebilirsiniz **`/clr`** . Örneğin, C++ aşağıdaki C# bildirimine eşdeğerdir:

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

Bunu onarmak için, dönüş türünü `Y::func` olarak değiştirin **`void`** .

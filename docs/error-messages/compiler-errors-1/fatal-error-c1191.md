---
description: 'Daha fazla bilgi edinin: önemli hata C1191'
title: Önemli hata C1191
ms.date: 11/04/2016
f1_keywords:
- C1191
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
ms.openlocfilehash: ef7f9ec6554daf0d83f3e597877509025512a6d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123584"
---
# <a name="fatal-error-c1191"></a>Önemli hata C1191

' dll ' yalnızca genel kapsamda içeri aktarılabilir

/CLR programlama kullanan bir programa mscorlib.dll içeri aktarma yönergesi bir ad alanında veya işlevde bulunamaz, ancak genel kapsamda gözükmelidir.

Aşağıdaki örnek C1191 oluşturur:

```cpp
// C1191.cpp
// compile with: /clr
namespace sample {
   #using <mscorlib.dll>   // C1191 not at global scope
}
```

Olası çözüm:

```cpp
// C1191b.cpp
// compile with: /clr /c
#using <mscorlib.dll>
namespace sample {}
```

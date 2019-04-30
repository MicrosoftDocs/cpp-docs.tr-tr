---
title: Derleyici Hatası C3117
ms.date: 11/04/2016
f1_keywords:
- C3117
helpviewer_keywords:
- C3117
ms.assetid: dceee392-d4c7-4599-b75e-7aaac7c36fdd
ms.openlocfilehash: 66efcf95599a18e0d93ff36f0e684ad350941977
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345536"
---
# <a name="compiler-error-c3117"></a>Derleyici Hatası C3117

'%$S': arabirimin yalnızca bir temel sınıf olabilir

Birden çok temel sınıftan devralınan bir arabirim bildirdiğiniz.

Aşağıdaki örnek, C3117 oluşturur:

```
// C3117.cpp
#include <windows.h>

[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface I1
{
};

[ object, uuid("00000000-0000-0000-0000-000000000002") ]
__interface I2
{
};

[ object, uuid("00000000-0000-0000-0000-000000000003") ]
__interface I3 : I1, I2
{   // C3117
};
```
---
title: Derleyici Hatası C3265
ms.date: 11/04/2016
f1_keywords:
- C3265
helpviewer_keywords:
- C3265
ms.assetid: 10ab3e17-4a9f-4120-bab5-21473869b70f
ms.openlocfilehash: a675567e23764a0b361cab4bef4bc75019de3756
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365851"
---
# <a name="compiler-error-c3265"></a>Derleyici Hatası C3265

bir yönetilen 'yönetilen yapısı' içinde bir yönetilmeyen 'yönetilmeyen yapı' bildiremez

Yönetilen bir nesnenin yönetilmeyen bir bağlamda içeremez.

Aşağıdaki örnek, C3265 yeniden oluşturur:

```
// C3265_2.cpp
// compile with: /clr /LD
#include <vcclr.h>

ref class A { };

class B
// try the following line instead
// ref class B
{
   A ^a;   // C3265
   // or embed the managed handle using gcroot
   // try the following line instead
   // gcroot<A^> a;
};
```

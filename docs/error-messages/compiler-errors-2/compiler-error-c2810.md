---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2810'
title: Derleyici hatası C2810
ms.date: 11/04/2016
f1_keywords:
- C2810
helpviewer_keywords:
- C2810
ms.assetid: f63e8f24-d7f6-42ac-904f-72ff49592ba6
ms.openlocfilehash: 609a1ccd89619ddb66b42a81cf9a769480670508
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320593"
---
# <a name="compiler-error-c2810"></a>Derleyici hatası C2810

' interface ': bir arabirim yalnızca başka bir arabirimden devralınabilir

[Arabirim](../../cpp/interface.md) yalnızca başka bir arabirimden devralınabilir ve bir sınıftan ya da yapıdan kalýtýmla eşleşmeyebilir.

Aşağıdaki örnek C2810 oluşturur:

```cpp
// C2810.cpp
#include <unknwn.h>
class CBase1 {
public:
  HRESULT mf1();
  int  m_i;
};

[object, uuid="40719E20-EF37-11D1-978D-0000F805D73B"]
__interface IDerived : public CBase1 {  // C2810
// try the following line instead
// __interface IDerived {
   HRESULT mf2(void *a);
};

struct CBase2 {
   HRESULT mf1(int a, char *b);
   HRESULT mf2();
};
```

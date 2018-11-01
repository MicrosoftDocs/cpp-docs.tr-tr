---
title: Derleyici Hatası C2861
ms.date: 11/04/2016
f1_keywords:
- C2861
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
ms.openlocfilehash: e7cced7a9abd974d0cbcea69059459d6c15f9850
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514705"
---
# <a name="compiler-error-c2861"></a>Derleyici Hatası C2861

'işlev adı': bir arabirim üye işlevi tanımlanamıyor

Derleyici arabirimi anahtar sözcüğü karşılaştı veya bir yapının bir arabirim olarak atanan ancak ardından üyesi bulundu işlev tanımı.  Bir arabirim üye işlevi için bir tanım içeriyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2861 oluşturur:

```
// C2861.cpp
// compile with: /c
#include <objbase.h>   // required for IUnknown definition
[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IMyInterface : IUnknown {
   HRESULT mf(int a);
};

HRESULT IMyInterface::mf(int a) {}   // C2861

```
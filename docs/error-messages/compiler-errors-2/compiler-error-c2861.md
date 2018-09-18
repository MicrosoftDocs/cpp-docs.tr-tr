---
title: Derleyici Hatası C2861 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2861
dev_langs:
- C++
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94210350e0483b46eb86579b837501a5291bda4d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037261"
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
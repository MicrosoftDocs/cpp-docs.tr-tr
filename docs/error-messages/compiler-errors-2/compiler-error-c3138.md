---
title: Derleyici hatası C3138
ms.date: 11/04/2016
f1_keywords:
- C3138
helpviewer_keywords:
- C3138
ms.assetid: 364ee9e8-9358-410e-bd35-9c4a226a3753
ms.openlocfilehash: 3980bebdae0301dfbbb3cea91d6631053a118995
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761264"
---
# <a name="compiler-error-c3138"></a>Derleyici hatası C3138

' interface ': bir ' Attribute ' arabirimi IDispatch 'ten devralınmalıdır veya IDispatch 'ten devralan bir arabirimden

[Dual](../../windows/dual.md) veya [dispınterface](../../windows/dispinterface.md) özniteliklerine sahip bir arabirim doğrudan veya dolaylı temel arabirim olarak `IDispatch` sahip değildir.

Aşağıdaki örnek C3138 oluşturur:

```cpp
// C3138.cpp
#include <unknwn.h>

[ object, uuid("77ac9240-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyCustomInterface
{
   HRESULT mf1(void);
};

[ dispinterface, uuid("3536f8a0-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyDispInterface : IUnknown
{
   [id(1)] HRESULT mf2(void);
};

[ object, dual, uuid("34e90a10-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyDualInterface : IMyCustomInterface  // C3138 expected
{
   HRESULT mf3(void);
};
```

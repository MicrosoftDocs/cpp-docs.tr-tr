---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4680'
title: Derleyici Uyarısı (düzey 4) C4680
ms.date: 11/04/2016
f1_keywords:
- C4680
helpviewer_keywords:
- C4680
ms.assetid: 6e043f4c-c601-4b77-8130-920cff1d912e
ms.openlocfilehash: 85f14273efb2b7d91a6b663e69918b77bcb7c597
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133880"
---
# <a name="compiler-warning-level-4-c4680"></a>Derleyici Uyarısı (düzey 4) C4680

' class ': coclass varsayılan bir arabirim belirtmiyor

[Coclass](../../windows/attributes/coclass.md) özniteliğiyle işaretlenmiş bir sınıf için [varsayılan](../../windows/attributes/default-cpp.md) bir arabirim belirtilmedi. Bir nesnenin faydalı olması için bir arabirim uygulaması gerekir.

Aşağıdaki örnek C4680 oluşturur:

```cpp
// C4680.cpp
// compile with: /W4
#include <windows.h>
[module(name="MyModule")];

[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface1
{
   HRESULT f1();
};

[ object, uuid(37331a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface2
{
   HRESULT f1();
};

// to resolve C4680, specify a source interface also
// for example, default(IMyIface1, IMyface2)
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f), default(IMyIface1), source(IMyIface1) ]
class CMyClass : public IMyIface1
{   // C4680
};

int main()
{
}
```

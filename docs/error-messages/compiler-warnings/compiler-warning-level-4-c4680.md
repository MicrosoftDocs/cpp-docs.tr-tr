---
title: Derleyici Uyarısı (düzey 4) C4680 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4680
dev_langs:
- C++
helpviewer_keywords:
- C4680
ms.assetid: 6e043f4c-c601-4b77-8130-920cff1d912e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06e4e9aa4c3c3cdef2c0d241a5636248290ac2e6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053797"
---
# <a name="compiler-warning-level-4-c4680"></a>Derleyici Uyarısı (düzey 4) C4680

'class': coclass varsayılan bir arabirim belirtmiyor

A [varsayılan](../../windows/default-cpp.md) arabirimi ile işaretlenmiş bir sınıf için belirtilmemiş [coclass'ı](../../windows/coclass.md) özniteliği. Sırayla kullanışlı olması bir nesne için bir arabirim uygulaması gerekir.

Aşağıdaki örnek, C4680 oluşturur:

```
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
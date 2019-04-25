---
title: Derleyici Uyarısı (düzey 4) C4680
ms.date: 11/04/2016
f1_keywords:
- C4680
helpviewer_keywords:
- C4680
ms.assetid: 6e043f4c-c601-4b77-8130-920cff1d912e
ms.openlocfilehash: 9130fa2665452b85c5ec83eef0b3d1d618c995a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226875"
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
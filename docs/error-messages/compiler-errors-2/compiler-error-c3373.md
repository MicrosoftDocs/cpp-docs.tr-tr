---
title: Derleyici Hatası C3373 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3373
dev_langs:
- C++
helpviewer_keywords:
- C3373
ms.assetid: 6e7586c3-1a15-4773-ad20-f90090a400dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 336380c5097979df459a8d8ac4f7776aa84513be
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024028"
---
# <a name="compiler-error-c3373"></a>Derleyici Hatası C3373

'öznitelik' özniteliği bir coclass'ta dışında herhangi bir bağımsız değişken alır.

Bazı öznitelikler C++ yapısı, ancak öznitelik bağımsız değişkenleri yalnızca bazı yapıları üzerinde izin verilmiyor olabilir birden uygulanabilir.

Aşağıdaki örnek, C3373 oluşturur:

```
// C3373.cpp
#include <windows.h>

[module(name="MyModule")];

[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface
{
   // arguments to source and restricted are not allowed when
   // these attributes are applied to an interface
   [source(IMyIface)] HRESULT f1();
   [restricted(IMyIface)] HRESULT f2(); // C3373
};

[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f) ]
class CMyClass : public IMyIface {
};

int main() {
}
```
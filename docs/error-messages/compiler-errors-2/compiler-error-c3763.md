---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3763'
title: Derleyici hatası C3763
ms.date: 11/04/2016
f1_keywords:
- C3763
helpviewer_keywords:
- C3763
ms.assetid: 58b1f079-cd1d-46e0-9431-ea18210106b7
ms.openlocfilehash: 9423c2f0db133c58fc7680b475a450c7190423f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285441"
---
# <a name="compiler-error-c3763"></a>Derleyici hatası C3763

' Type ': ' retval ' ve ' Out ' yalnızca bir veri işaretçisi türünde yer alabilir

[Out](../../windows/attributes/out-cpp.md) veya [retval](../../windows/attributes/retval.md) öznitelikleri yalnızca işaretçi türündeki parametrelerde bulunabilir. Özniteliği kaldırın ya da işaretçiyi tür işaretçisi olarak yapın.

Aşağıdaki örnek C3763 oluşturur:

```cpp
// C3763.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlplus.h>
#include <atlcom.h>

[ module(name=test) ];

[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IF84 : IDispatch
{
   [id(0x00000002)]HRESULT m2([out]unsigned char);
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]
class CF84 : public IF84
{   // C3763
public:
   HRESULT __stdcall m2(unsigned char i)
   {
      return S_OK;
   }
};

int main()
{
}
```

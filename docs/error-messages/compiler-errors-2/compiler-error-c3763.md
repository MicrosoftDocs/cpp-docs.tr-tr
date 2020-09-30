---
title: Derleyici hatası C3763
ms.date: 11/04/2016
f1_keywords:
- C3763
helpviewer_keywords:
- C3763
ms.assetid: 58b1f079-cd1d-46e0-9431-ea18210106b7
ms.openlocfilehash: 7ccb3d846982bbf9a52a7267549f6481b5a1bd9b
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503959"
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

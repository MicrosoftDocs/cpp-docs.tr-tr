---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3508'
title: Derleyici hatası C3508
ms.date: 11/04/2016
f1_keywords:
- C3508
helpviewer_keywords:
- C3508
ms.assetid: 16d08f89-2f32-44eb-9421-68acecddf49b
ms.openlocfilehash: 74dff625c3c1855fa828f0fc492d9839e5c7f67c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315445"
---
# <a name="compiler-error-c3508"></a>Derleyici hatası C3508

' Type ': geçerli bir Otomasyon türü değil

Geçersiz bir tür belirtildi.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3508 oluşturur:

```cpp
// C3508.cpp
#define _ATL_DEBUG_QI

#define WIN32_LEAN_AND_MEAN
#define STRICT
#ifndef _WIN32_WINNT
#define _WIN32_WINNT 0x0400
#endif

#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
extern CComModule _Module;
#include <atlcom.h>
#include <atlctl.h>
#include <atlstr.h>

extern "C" int printf_s(const char*, ...);

[module(name=oso)];

union U
// try the following two lines instead
// [export]
// struct U
{
   int i, j;
};

[dispinterface]
__interface I
{
   [id(1)] HRESULT func(U* u);
};

[coclass]
struct C : I
{
   HRESULT func(U*)   // C3508
   {
      return E_FAIL;
   }
};

int main()
{
}
```

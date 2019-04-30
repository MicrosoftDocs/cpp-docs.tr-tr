---
title: Derleyici Hatası C3761
ms.date: 11/04/2016
f1_keywords:
- C3761
helpviewer_keywords:
- C3761
ms.assetid: 0c16f093-7a78-4838-b90b-0c67ef6e9270
ms.openlocfilehash: c78709acfafabbc6d6bc24979432a93e899c3208
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400285"
---
# <a name="compiler-error-c3761"></a>Derleyici Hatası C3761

'function': 'retval' yalnızca işlevin son bağımsız değişken üzerinde görünür

[Retval](../../windows/retval.md) özniteliği, listedeki son bağımsız değişken olmayan işlev bağımsız değişkenleri üzerinde kullanıldı.

Aşağıdaki örnek, C3761 oluşturur:

```
// C3761.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(name=test) ];

[dispinterface]
__interface I
{
   [id(1)] HRESULT func([out, retval] int* i, [in] int j);
   // try the following line instead
   // [id(1)] HRESULT func([in] int i, [out, retval] int* j);
};

[coclass]
struct C : I {   // C3761
   HRESULT func(int* i, int j)
   // try the following line instead
   // HRESULT func(int j, int* i)
   {
      return S_OK;
   }
};

int main()
{
}
```
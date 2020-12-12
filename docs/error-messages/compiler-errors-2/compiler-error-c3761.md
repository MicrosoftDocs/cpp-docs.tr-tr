---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3761'
title: Derleyici hatası C3761
ms.date: 11/04/2016
f1_keywords:
- C3761
helpviewer_keywords:
- C3761
ms.assetid: 0c16f093-7a78-4838-b90b-0c67ef6e9270
ms.openlocfilehash: c3fd33d7a27d8ae85582a5711b7bdd1e15c93393
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255463"
---
# <a name="compiler-error-c3761"></a>Derleyici hatası C3761

' function ': ' retval ' yalnızca bir işlevin son bağımsız değişkeninde yer alabilir

[Retval](../../windows/attributes/retval.md) özniteliği, listedeki son bağımsız değişken olmayan bir işlev bağımsız değişkeninde kullanıldı.

Aşağıdaki örnek C3761 oluşturur:

```cpp
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

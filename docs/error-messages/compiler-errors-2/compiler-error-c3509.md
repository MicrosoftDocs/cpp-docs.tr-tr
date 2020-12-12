---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3509'
title: Derleyici hatası C3509
ms.date: 11/04/2016
f1_keywords:
- C3509
helpviewer_keywords:
- C3509
ms.assetid: cc2db39a-2f98-4e40-b803-496e585494e6
ms.openlocfilehash: 58accbf4d408a2d0ce4181b0ab35db003d2d6f39
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113148"
---
# <a name="compiler-error-c3509"></a>Derleyici hatası C3509

' Type ': geçersiz Otomasyon dönüş türü; bir parametre ' retval ' olarak işaretlendiğinde, dönüş türü ' void ', ' HRESULT ' veya ' SCODE ' olmalıdır

COM arabirimindeki bir Yöntem void ya da HRESULT döndürmelidir.

Aşağıdaki örnek C3509 oluşturur:

```cpp
// C3509.cpp
#define _ATL_DEBUG_QI

#define WIN32_LEAN_AND_MEAN   // Exclude rarely-used stuff from Windows headers
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

[module(name=oso)];

[dispinterface, uuid(00000000-0000-0000-0000-000000000001)]
__interface I {
   [id(1)] int f([out, retval] int*);   // C3509
   // try the following line instead
   // [id(1)] void f([out, retval] int*);
};

[coclass, uuid(00000000-0000-0000-0000-000000000002)]
struct C : I {
   int f(int*) {
   // try the following line instead, and delete return statement
   // void f(int*) {
      return 0;
   }
};

int main() {
}
```

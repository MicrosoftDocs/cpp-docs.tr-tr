---
title: Derleyici hatası C3733
ms.date: 11/04/2016
f1_keywords:
- C3733
helpviewer_keywords:
- C3733
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
ms.openlocfilehash: 961aa0caf31d49917f6df67305bc01d465884b68
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165905"
---
# <a name="compiler-error-c3733"></a>Derleyici hatası C3733

' Event ': bir COM olayı belirtmek için yanlış sözdizimi; ' __interface ' öğesini unuttunuz mu?

Bir COM olayı için yanlış sözdizimi kullanıldı. Bu hatayı düzeltmek için, olay türünü değiştirin veya sözdizimini, COM olay kurallarıyla uyumlu olacak şekilde düzeltin.

Aşağıdaki örnek C3733 oluşturur:

```
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[coclass, event_source(com), // change 'com' to 'native' to resolve
uuid("00000000-0000-0000-0000-000000000001")]
class A
{
   __event void func();   // C3733
};

int main()
{
}
```

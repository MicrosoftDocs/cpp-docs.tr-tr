---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3733'
title: Derleyici hatası C3733
ms.date: 11/04/2016
f1_keywords:
- C3733
helpviewer_keywords:
- C3733
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
ms.openlocfilehash: 768586c760a06c502a08a8a11b8a1ad4e33c4e93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245024"
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

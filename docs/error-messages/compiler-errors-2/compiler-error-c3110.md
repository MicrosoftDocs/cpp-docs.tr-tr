---
title: Derleyici hatası C3110
ms.date: 11/04/2016
f1_keywords:
- C3110
helpviewer_keywords:
- C3110
ms.assetid: 821dc71f-896e-4b2d-af0e-aa9932934b7b
ms.openlocfilehash: 9eb3e54b8bd9b296ad9cd7e0b6ea2943c74d1dff
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91498485"
---
# <a name="compiler-error-c3110"></a>Derleyici hatası C3110

' function_name ': bir COM arabirimi yöntemini aşırı yükleyemezsiniz

Bir arabirim özniteliği tarafından önceden ortaya çıkacak bir arabirim, örneğin:

- [Özel](../../windows/attributes/custom-cpp.md)

- [dispinterface](../../windows/attributes/dispinterface.md)

- [çift](../../windows/attributes/dual.md)

- [object](../../windows/attributes/object-cpp.md)

aşırı yüklenemez. Örnek:

```cpp
// C3110.cpp
#include <unknwn.h>
[ object, uuid= "4F98A180-EF37-11D1-978D-0000F805D73B" ]
__interface ITestInterface
{
   HRESULT mf1(void);
   HRESULT mf1(BSTR); // C3110
};

int main()
{
}
```

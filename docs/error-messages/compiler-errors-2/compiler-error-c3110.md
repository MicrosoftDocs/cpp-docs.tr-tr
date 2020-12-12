---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3110'
title: Derleyici hatası C3110
ms.date: 11/04/2016
f1_keywords:
- C3110
helpviewer_keywords:
- C3110
ms.assetid: 821dc71f-896e-4b2d-af0e-aa9932934b7b
ms.openlocfilehash: 1e402941ea88a34c48f58df56a365f74c819a8e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116060"
---
# <a name="compiler-error-c3110"></a>Derleyici hatası C3110

' function_name ': bir COM arabirimi yöntemini aşırı yükleyemezsiniz

Bir arabirim özniteliği tarafından önceden ortaya çıkacak bir arabirim, örneğin:

- [Özel](../../windows/attributes/custom-cpp.md)

- [dispinterface](../../windows/attributes/dispinterface.md)

- [Çift](../../windows/attributes/dual.md)

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

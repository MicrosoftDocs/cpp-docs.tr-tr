---
title: Derleyici Hatası C2788
ms.date: 11/04/2016
f1_keywords:
- C2788
helpviewer_keywords:
- C2788
ms.assetid: 8688fc5c-e652-43b4-b407-9c488c76f2db
ms.openlocfilehash: 0025aa5211c2736860bdd30cad4315f63fba9337
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460911"
---
# <a name="compiler-error-c2788"></a>Derleyici Hatası C2788

'identifier': Bu nesneyle ilişkili birden fazla GUID

[__Uuidof](../../cpp/uuidof-operator.md) işleci ile bağlı bir GUID veya böyle bir kullanıcı tanımlı türde bir nesne kullanıcı tanımlı bir tür alır. Bağımsız değişken bir nesne birden çok GUID'yi olduğunda bu hata oluşur.

Aşağıdaki örnek, C2788 oluşturur:

```
// C2788.cpp
#include <windows.h>
struct __declspec(uuid("00000001-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000002-0000-0000-0000-000000000000}")) B {};
template <class T, class U> class MyClass {};

typedef MyClass<A,B> MyBadClass;
typedef MyClass<A,A> MyGoodClass;

int main() {
   __uuidof(MyBadClass);    // C2788
   // try the following line instead
   __uuidof(MyGoodClass);
}
```
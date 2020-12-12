---
description: 'Daha fazla bilgi edinin: void (C++)'
title: void (C++)
ms.date: 11/04/2016
f1_keywords:
- void_cpp
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
ms.openlocfilehash: e49dfa03e289cdbace50a24cf6854d25c51b3426
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213357"
---
# <a name="void-c"></a>void (C++)

İşlev dönüş türü olarak kullanıldığında **`void`** anahtar sözcüğü, işlevin bir değer döndürmediğinden emin olarak belirtir. İşlevin parametre listesi için kullanıldığında, **`void`** işlevin parametre aldığını belirtir. Bir işaretçinin bildiriminde kullanıldığında, **`void`** işaretçinin "Universal" olduğunu belirtir.

Bir işaretçinin türü **void \* _ ise, işaretçi `const` _ veya anahtar sözcüğüyle *bildirilmeyen herhangi bir değişkene işaret edebilir*** **`volatile`** . Bir **void \** _ işaretçisine başka bir türe yayınlanmadığı takdirde başvuru yapılamaz. _*Void \**_ bir işaretçi, herhangi bir diğer veri işaretçisi türüne dönüştürülebilir.

_ *`void`* * İşaretçisi bir işlevi işaret edebilir, ancak C++ içindeki bir sınıf üyesine yönelik değildir.

Türünde bir değişken bildiremezsiniz **`void`** .

## <a name="example"></a>Örnek

```cpp
// void.cpp
void vobject;   // C2182
void *pv;   // okay
int *pint; int i;
int main() {
   pv = &i;
   // Cast optional in C required in C++
   pint = (int *)pv;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[Yerleşik türler](../cpp/fundamental-types-cpp.md)

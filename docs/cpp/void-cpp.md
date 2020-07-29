---
title: void (C++)
ms.date: 11/04/2016
f1_keywords:
- void_cpp
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
ms.openlocfilehash: fddfc2e3295552414a00692006ab12725dc07d52
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213118"
---
# <a name="void-c"></a>void (C++)

İşlev dönüş türü olarak kullanıldığında **`void`** anahtar sözcüğü, işlevin bir değer döndürmediğinden emin olarak belirtir. İşlevin parametre listesi için kullanıldığında, **`void`** işlevin parametre aldığını belirtir. Bir işaretçinin bildiriminde kullanıldığında, **`void`** işaretçinin "Universal" olduğunu belirtir.

Bir işaretçinin türü ** \* void**ise, işaretçi **`const`** veya anahtar sözcüğüyle bildirilmeyen herhangi bir değişkene işaret edebilir **`volatile`** . Başka bir türe yayınlanmadığı için **void \* ** işaretçisine başvuru yapılamaz. **Void \* ** bir işaretçi, herhangi bir diğer veri işaretçisi türüne dönüştürülebilir.

Bir **`void`** işaretçi bir işlevi işaret edebilir, ancak C++ içindeki bir sınıf üyesine uygulanmaz.

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

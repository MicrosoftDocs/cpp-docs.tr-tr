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
ms.openlocfilehash: 2de019f908942a58b232877fcd9eebc4689d8e22
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187485"
---
# <a name="void-c"></a>void (C++)

İşlev dönüş türü olarak kullanıldığında, **void** anahtar sözcüğü işlevin bir değer döndürmediğinden emin olarak belirtir. İşlevin parametre listesi için kullanıldığında, **void** işlevin hiçbir parametre aldığını belirtir. Bir işaretçinin bildiriminde kullanıldığında, **void** , işaretçinin "Universal" olduğunu belirtir.

Bir işaretçinin türü **\*void** ise, işaretçi **const** veya **volatile** anahtar sözcüğüyle bildirilmeyen herhangi bir değişkene işaret edebilir. **Void\*** işaretçisi, başka bir türe yayınlanmadığı takdirde başvuru yapılamaz. **Void\*** işaretçisi, başka bir tür veri işaretçisine dönüştürülebilir.

**Void** bir işaretçi bir işlevi işaret edebilir, ancak içindeki C++bir sınıf üyesine yönelik değildir.

**Void**türünde bir değişken bildiremezsiniz.

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

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Yerleşik türler](../cpp/fundamental-types-cpp.md)

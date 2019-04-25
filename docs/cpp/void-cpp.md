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
ms.openlocfilehash: cb4be000c3c41862d5b4df766d21ae1cddeb6838
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243997"
---
# <a name="void-c"></a>void (C++)

İşlev dönüş türü kullanıldığında **void** anahtar sözcüğü işlevin bir değer döndürmediğini belirtir. İşlevin parametre listesi için kullanıldığında, void işlevin parametre almadığını belirtir. Bir işaretçinin bildiriminde kullanıldığında, void işaretçinin "evrensel" olduğunu belirtir.

Bir işaretçinin türü ise `void *`, işaretçi ile bildirilmedi herhangi bir değişken işaret edebilir **const** veya **geçici** anahtar sözcüğü. Başka bir türe atanmadığı sürece bir void işaretçisine tekrar başvurulamaz. Void bir işaretçi başka türde veri işaretçisine dönüştürülebilir.

Void bir işaretçi, bir işlevi gösterebilir ancak C++'ta bir sınıf üyesini gösteremez.

Void türünün değişkeninin bildirimini yapamazsınız.

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
[Temel Türler](../cpp/fundamental-types-cpp.md)
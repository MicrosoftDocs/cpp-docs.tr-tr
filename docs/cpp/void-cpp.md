---
title: geçersiz kılma (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- void_cpp
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1aab4a8c18424fdbd52ac24444dd35a1660a714b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114351"
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
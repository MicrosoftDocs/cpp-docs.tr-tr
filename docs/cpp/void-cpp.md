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
ms.openlocfilehash: 7d01d5b50cb347736bbd2a42fb76811bdfdb546c
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245203"
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
[Temel Türler](../cpp/fundamental-types-cpp.md)
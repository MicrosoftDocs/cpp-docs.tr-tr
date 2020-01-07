---
title: __int8, __int16, __int32, __int64
ms.date: 10/09/2018
f1_keywords:
- __int8_cpp
- __int16_cpp
- __int32_cpp
- __int64_cpp
- __int8
- __int16
- __int32
- __int64
- _int8
- _int16
- _int32
- _int64
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type [C++], integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
ms.openlocfilehash: 4e793f23581f7dc62a39fcd8c5c504fb5a2ccbc9
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301476"
---
# <a name="__int8-__int16-__int32-__int64"></a>__int8, __int16, __int32, __int64

**Microsoft 'a özgü**

Microsoft C/C++ özellikleri, boyutlandırılmış tamsayı türlerini destekler. 8, 16-, 32-veya 64-bit tamsayı değişkenlerini **__int**<em>n</em> tür belirleyicisi kullanarak bildirebilirsiniz; burada *n* 8, 16, 32 veya 64.

Aşağıdaki örnekte, bu tür boyutlandırılmış tamsayıların her biri için bir değişken bildirilir:

```cpp
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

**__İnt8**, **__int16**ve **__INT32** türleri aynı boyutta olan ANSI türleri için eş anlamlılardır ve birden çok platformda aynı şekilde davranan taşınabilir kod yazmak için yararlıdır. **__İnt8** veri türü **char**türü ile eşanlamlı, **__int16** tür **Short**ile eşanlamlı ve **__int32** **int**türü ile eşanlamlı bir tür. **__İnt64** türü **Long Long**ile eşanlamlı bir tür.

Önceki sürümlerle uyumluluk için **_int8**, **_int16**, **_int32**ve **_Int64** , [/za __int8 dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde **__int16**, **__int32**, **__int64**ve **\(** için eş anlamlılardır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir __int*xx* parametresinin **int**'e Yükseltilecek olduğunu gösterir:

```cpp
// sized_int_types.cpp

#include <stdio.h>

void func(int i) {
    printf_s("%s\n", __FUNCTION__);
}

int main()
{
    __int8 i8 = 100;
    func(i8);   // no void func(__int8 i8) function
                // __int8 will be promoted to int
}
```

```Output
func
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Yerleşik türler](../cpp/fundamental-types-cpp.md)<br/>
[Veri Türü Aralıkları](../cpp/data-type-ranges.md)<br/>

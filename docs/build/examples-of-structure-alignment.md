---
title: Yapı Hizalama Örnekleri
ms.date: 03/26/2018
helpviewer_keywords:
- structure alignment
- examples [C++], structure alignment
ms.assetid: 03d137bf-5cc4-472e-9583-6498f2534199
ms.openlocfilehash: 27f7e89b1c7faec06347d8760247a76a33e0b91e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466254"
---
# <a name="examples-of-structure-alignment"></a>Yapı Hizalama Örnekleri

Hizalanmış bir yapı veya birleşim ve karşılık gelen rakamları, yapı veya birleşim bellekte düzenini gösteren aşağıdaki dört örnek her bildirin. Her sütunda bir şekil bellek baytını temsil eder ve öteleme bu bayt sayısı sütunundaki sayıyı belirtir. Her Şekil ikinci satırındaki adı bir Değişken bildiriminde adını karşılık gelir. Gölgeli sütunlar doldurmayı belirtilen hizalama ulaşmak için gerekli olan gösterir.

## <a name="example-1"></a>Örnek 1

```C
// Total size = 2 bytes, alignment = 2 bytes (word).

_declspec(align(2)) struct {
    short a;      // +0; size = 2 bytes
}
```

![AMD dönüştürme örnek](../build/media/vcamd_conv_ex_1_block.png "vcAmd_conv_ex_1")

## <a name="example-2"></a>Örnek 2

```C
// Total size = 24 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) struct {
    int a;       // +0; size = 4 bytes
    double b;    // +8; size = 8 bytes
    short c;     // +16; size = 2 bytes
}
```

![AMD dönüştürme örnek](../build/media/vcamd_conv_ex_2_block.png "vcAmd_conv_ex_2")

## <a name="example-3"></a>Örnek 3

```C
// Total size = 22 bytes, alignment = 4 bytes (doubleword).

_declspec(align(4)) struct {
    char a;       // +0; size = 1 byte
    short b;      // +2; size = 2 bytes
    char c;       // +4; size = 1 byte
    int d;        // +8; size = 4 bytes
}
```

![AMD dönüştürme örnek](../build/media/vcamd_conv_ex_3_block.png "vcAmd_conv_ex_3")

## <a name="example-4"></a>Örnek 4

```C
// Total size = 8 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) union {
    char *p;      // +0; size = 8 bytes
    short s;      // +0; size = 2 bytes
    long l;       // +0; size = 4 bytes
}
```

![AMD dönüştürme örnek](../build/media/vcamd_conv_ex_4_block.png "vcAmd_conv_ex_4")

## <a name="see-also"></a>Ayrıca bkz.

[Türler ve Depolama](../build/types-and-storage.md)<br/>

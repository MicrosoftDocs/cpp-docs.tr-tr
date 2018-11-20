---
title: Yapı Hizalama Örnekleri
ms.date: 11/19/2018
helpviewer_keywords:
- structure alignment
- examples [C++], structure alignment
ms.assetid: 03d137bf-5cc4-472e-9583-6498f2534199
ms.openlocfilehash: 7c4b3ae29674e9c4fc27e8e175867339001b9a0d
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175346"
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

![AMD dönüştürme örnek 1 yapısı Düzen](../build/media/vcamd_conv_ex_1_block.png "AMD dönüştürme örnek 1 yapısı düzeni")

## <a name="example-2"></a>Örnek 2

```C
// Total size = 24 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) struct {
    int a;       // +0; size = 4 bytes
    double b;    // +8; size = 8 bytes
    short c;     // +16; size = 2 bytes
}
```

![AMD dönüştürme örnek 2 yapısı Düzen](../build/media/vcamd_conv_ex_2_block.png "AMD dönüştürme örnek 2 yapısı düzeni")

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

![AMD dönüştürme örnek 2 yapısı Düzen](../build/media/vcamd_conv_ex_3_block.png "AMD dönüştürme örnek 2 yapısı düzeni")

## <a name="example-4"></a>Örnek 4

```C
// Total size = 8 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) union {
    char *p;      // +0; size = 8 bytes
    short s;      // +0; size = 2 bytes
    long l;       // +0; size = 4 bytes
}
```

![AMD dönüştürme örnek 4 birleşim layouit](../build/media/vcamd_conv_ex_4_block.png "AMD dönüştürme örnek 4 birleşim layouit")

## <a name="see-also"></a>Ayrıca bkz.

[Türler ve Depolama](../build/types-and-storage.md)<br/>

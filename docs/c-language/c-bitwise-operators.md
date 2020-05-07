---
title: C Bit Düzeyinde İşleçler
ms.date: 01/29/2018
helpviewer_keywords:
- '| operator, bitwise operators'
- bitwise operators, Visual C
- bitwise operators
- operators [C], bitwise
- ^ operator, bitwise operators
- AND operator
- ampersand operator (&)
- ^ operator
- '& operator, bitwise operators'
ms.assetid: e22127b1-9a2d-4876-b01d-c8f72cec3317
ms.openlocfilehash: 50be8ae38f21d0a9f46c180abf179e1358b707cd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168779"
---
# <a name="c-bitwise-operators"></a>C Bit Düzeyinde İşleçler

Bit düzeyinde işleçler bit düzeyinde AND (**&**), bit düzeyinde dışlamalı veya (**^**) ve bit düzeyinde kapsamlı veya (**&#124;**) işlemleri gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

*Ve-ifadesi*: &nbsp; &nbsp; *eşitlik-ifade* &nbsp; &nbsp; *ve-ifade* **&** *eşitlik-ifade*

*dışlamalı OR ifadesi*: &nbsp; &nbsp; *and ifadesi* &nbsp; &nbsp; *dışlamalı-OR-* **^** ifadesi *ve-* ifadesi

*kapsamlı or*-ifadesi: &nbsp; &nbsp; *dışlamalı* &nbsp; &nbsp;veya ifade &#124; *dışlamalı* *-or-* ifadesi

Bit düzeyinde işleçlerin işlenenleri integral türlerine sahip olmalıdır, ancak türleri farklı olabilir. Bu işleçler, her zamanki aritmetik dönüştürmeleri gerçekleştirir; sonucun türü, dönüştürmeden sonra işlenen türüdür.

C bit düzeyinde işleçler aşağıda açıklanmıştır:

|İşleç|Açıklama|
|--------------|-----------------|
|**&**|Bit düzeyinde AND işleci, ilk işleneninin her bir bitini ikinci işleneninin karşılık gelen bitine karşılaştırır. Her iki bit de 1 ise, karşılık gelen sonuç biti 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç biti 0 olarak ayarlanır.|
|**^**|Bit düzeyinde dışlamalı OR işleci, ilk işleneninin her bir bitini ikinci işleneninin karşılık gelen bitine göre karşılaştırır. Bir bit 0 ise ve diğer bit 1 ise, karşılık gelen sonuç biti 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç biti 0 olarak ayarlanır.|
|**&#124;**|Bit düzeyinde kapsamlı OR işleci, ilk işleneninin her bir bitini ikinci işleneninin karşılık gelen bitine göre karşılaştırır. Her iki bit de 1 ise, karşılık gelen sonuç biti 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç biti 0 olarak ayarlanır.|

## <a name="examples"></a>Örnekler

Bu bildirimler aşağıdaki üç örnek için kullanılır:

```C
short i = 0xAB00;
short j = 0xABCD;
short n;

n = i & j;
```

Bu ilk örnekte atanan `n` sonuç, (0xab00 onaltılık) `i` ile aynıdır.

```C
n = i | j;

n = i ^ j;
```

Bit düzeyinde kapsamlı veya ikinci örnekte, 0xABCD (onaltılı) değeri, bit düzeyinde dışlamalı veya üçüncü örnekte 0xCD (onaltılı) üretilirken oluşur.

**Microsoft'a Özgü**

İşaretli tamsayılar üzerinde bit düzeyinde işlemin sonuçları, ANSI C standardına göre uygulama tarafından tanımlanır. Microsoft C derleyicisi için, işaretli tamsayıların bit düzeyinde işlemleri işaretsiz tamsayılar üzerinde bit tabanlı işlemlerle aynı şekilde çalışır. Örneğin, `-16 & 99` ikili dosyada şu şekilde ifade edilebilir

```Expression
  11111111 11110000
& 00000000 01100011
  _________________
  00000000 01100000
```

Bit düzeyinde ve 96 Decimal 'in sonucu.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bit Düzeyinde AND İşleci: &](../cpp/bitwise-and-operator-amp.md)<br/>
[Bit düzeyinde dışlamalı OR Işleci: ^](../cpp/bitwise-exclusive-or-operator-hat.md)<br/>
[Bit düzeyinde kapsamlı OR Işleci: &#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)

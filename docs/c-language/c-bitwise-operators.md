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
ms.openlocfilehash: 2133aaa5faa0f4bef7391fb5c0e7e0eb51fd4e69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543379"
---
# <a name="c-bitwise-operators"></a>C Bit Düzeyinde İşleçler

Bit düzeyinde işleçler bit düzeyinde gerçekleştirmek- ve (**&**), bit düzeyinde dışlamalı OR (**^**) ve bit düzeyinde kapsamalı OR (**&#124;**) işlemler.

## <a name="syntax"></a>Sözdizimi

*VE ifade*: &nbsp; &nbsp; *eşitlik ifade* &nbsp; &nbsp; *ve ifade* **&** *eşitlik ifadesi*

*dışlamalı OR ifadesi*: &nbsp; &nbsp; *ve ifade* &nbsp; &nbsp; *dışlamalı OR ifadesi* **^** *Ve ifade*

*OR ifadesi kapsamlı*: &nbsp; &nbsp; *dışlamalı OR ifadesi* &nbsp; &nbsp; *OR ifadesi kapsamlı* &#124; *dışlamalı OR ifadesi*

Bit düzeyinde işleçler işleneni integral türleri olması gerekir, ancak bunların türlerini farklı olabilir. Bu işleçlerden her zamanki aritmetik dönüşümleri gerçekleştirir; Sonuç türü dönüştürme işleminden sonra işlenenler türüdür.

C bit düzeyinde işleçler aşağıda açıklanmıştır:

|İşleç|Açıklama|
|--------------|-----------------|
|**&**|Bitwise- ve karşılık gelen bit ikinci işlenenin ilk işlenenin her bitini işleci karşılaştırır. Her iki bit 1 ise, karşılık gelen sonuç bit 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç bit 0 olarak ayarlanır.|
|**^**|Bit düzeyinde dışlamalı OR işleci, ikinci işlenenin karşılık gelen bit ilk işlenenin her bitini karşılaştırır. Bir bit 0'dır ve 1 diğer bit ise, karşılık gelen sonuç bit 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç bit 0 olarak ayarlanır.|
|**&#124;**|Bit düzeyinde kapsamalı OR işleci, ikinci işlenenin karşılık gelen bit ilk işlenenin her bitini karşılaştırır. Her iki bit 1 ise, karşılık gelen sonuç bit 1 olarak ayarlanır. Aksi takdirde, karşılık gelen sonuç bit 0 olarak ayarlanır.|

## <a name="examples"></a>Örnekler

Bu bildirimler, aşağıdaki üç örnekleri için kullanılır:

```C
short i = 0xAB00;
short j = 0xABCD;
short n;

n = i & j;
```

Atanan sonucu `n` bu ilk örnekte aynıdır `i` (onaltılık 0xAB00).

```C
n = i | j;

n = i ^ j;
```

Bit düzeyinde özel veya üçüncü örnek 0xCD (onaltılık düzende) üretir ancak ikinci örnekte bit düzeyinde kapsamalı OR değeri (onaltılı) 0xABCD sonuçlanır.

**Microsoft'a özgü**

İmzalı tamsayılar üzerinde bit düzeyinde işlem sonuçlarını ANSI C standardı göre uygulama tanımlı. Microsoft C derleyicisi için işaretsiz tamsayılarda bit düzeyinde işlemler aynı işaretli tamsayılarda bit düzeyinde çalışır. Örneğin, `-16 & 99` ikili olarak ifade edilebilir

```Expression
  11111111 11110000
& 00000000 01100011
  _________________
  00000000 01100000
```

Bit düzeyinde AND'in sonucu 96 ondalık ' dir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bit Düzeyinde AND İşleci: &](../cpp/bitwise-and-operator-amp.md)<br/>
[Bit Düzeyinde Özel OR İşleci: ^](../cpp/bitwise-exclusive-or-operator-hat.md)<br/>
[Bit düzeyinde kapsamlı OR işleci:&#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)
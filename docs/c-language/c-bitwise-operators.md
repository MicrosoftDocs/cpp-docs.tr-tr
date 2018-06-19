---
title: C bit düzeyinde işleçler | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c5c360246282f8b6062d21061856a57bd2c7194
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384339"
---
# <a name="c-bitwise-operators"></a>C Bit Düzeyinde İşleçler

Bit düzeyinde işleçler Bitsel gerçekleştirmek- ve (**&**), özel veya bit düzeyinde (**^**) ve bit düzeyinde-(bunlar dahil)-OR (**&#124;**) işlemler.

## <a name="syntax"></a>Sözdizimi

*VE ifade*:  
&nbsp;&nbsp;*Eşitlik ifade*  
&nbsp;&nbsp;*VE ifade* **&** *eşitlik ifade*

*dışlayan OR ifadesi*:  
&nbsp;&nbsp;*VE ifade*  
&nbsp;&nbsp;*dışlayan OR ifadesi* **^** *ve ifade*

*OR ifadesi dahil*:  
&nbsp;&nbsp;*dışlayan OR ifadesi*  
&nbsp;&nbsp;*OR ifadesi dahil* &#124; *özel veya ifade*

Bit düzeyinde işleçler işlenenleri tam sayı türleri olması gerekir, ancak bunların türlerine farklı olabilir. Bu işleçlere olağan aritmetik dönüştürmeler; yine de gerçekleştir istiyor musunuz? Sonuç türü dönüştürmeden sonra işlenen türüdür.

C bit düzeyinde işleçler aşağıda açıklanmıştır:

|İşleç|Açıklama|
|--------------|-----------------|
|**&**|Bit düzeyinde- ve her bit kendi ilk işleneninin ikinci işleneninin karşılık gelen bit işleci karşılaştırır. Her iki BITS 1 ise, karşılık gelen sonuç bit 1 olarak ayarlanır. Aksi halde, karşılık gelen sonuç bit 0 olarak ayarlanır.|
|**^**|Bit düzeyinde-özel-OR işleci, ilk işleneninin ikinci işleneninin karşılık gelen bit her bit karşılaştırır. Bir bit 0'dır ve diğer bit 1 ise, karşılık gelen sonuç biti 1 olarak ayarlanır. Aksi halde, karşılık gelen sonuç bit 0 olarak ayarlanır.|
|**&#124;**|Bit düzeyinde-(bunlar dahil)-OR işleci, kendi ilk işleneninin ikinci işleneninin karşılık gelen bit her bit karşılaştırır. Her iki bit 1 ise, karşılık gelen sonuç bit 1 olarak ayarlanır. Aksi halde, karşılık gelen sonuç bit 0 olarak ayarlanır.|

## <a name="examples"></a>Örnekler

Bu bildirimler, aşağıdaki üç örnekler için kullanılır:

```C
short i = 0xAB00;
short j = 0xABCD;
short n;

n = i & j;
```

Atanan sonuç `n` bu ilk örnek aynıdır `i` (0xAB00 onaltılı).

```C
n = i | j;

n = i ^ j;
```

Bit düzeyinde özel OR Üçüncü örnekte 0xCD (onaltılık) üretir sırada ikinci örnekte dahil bit düzeyinde OR değeri (onaltılı) 0xABCD sonuçlanır.

**Microsoft özel**

İmzalı tamsayılar Bitsel işlemi sonuçlarını uygulama tanımlı standart ANSI C göre. İçin Microsoft C derleyicisi, imzasız tamsayılar üzerinde bit düzeyinde işlemler aynı bit düzeyinde işlemler imzalı tamsayılar üzerinde çalışır. Örneğin, `-16 & 99` binary olarak ifade edilebilir

```Expression
  11111111 11110000
& 00000000 01100011
  _________________
  00000000 01100000
```

Bit düzeyinde AND 96 ondalık sonucudur.

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

[Bit Düzeyinde AND İşleci: &](../cpp/bitwise-and-operator-amp.md)  
[Bit Düzeyinde Özel OR İşleci: ^](../cpp/bitwise-exclusive-or-operator-hat.md)  
[Bit düzeyinde kapsamlı OR işleci:&#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)  
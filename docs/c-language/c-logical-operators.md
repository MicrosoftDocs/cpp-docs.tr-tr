---
description: 'Daha fazla bilgi edinin: C mantıksal işleçleri'
title: C mantıksal işleçleri
ms.date: 06/14/2018
helpviewer_keywords:
- logical operators, expression sequence points
- logical operators, C
- logical AND operator
- '|| operator'
- operators [C], logical
- short-circuit evaluation
- '&& operator'
- logical OR operator
ms.assetid: c0a4e766-ad56-4300-bf76-b28dc0e19b43
ms.openlocfilehash: 58527e4702abce6d05f7f8e6d5aed2d7c17eca94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300313"
---
# <a name="c-logical-operators"></a>C mantıksal işleçleri

Mantıksal işleçler mantıksal-ve ( **&&** ) ve MANTıKSAL OR ( **||** ) işlemleri gerçekleştirir.

## <a name="syntax"></a>Syntax

*MANTıKSAL and-ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*kapsamlı OR ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*MANTıKSAL and ifadesi* **&&** *KAPSAMLı or ifadesi*    

*MANTıKSAL or ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal AND ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;mantıksal *or* -ifadesi **&#124;&#124;** *mantıksal and ifadesi*    

## <a name="remarks"></a>Açıklamalar

Mantıksal işleçler, olağan aritmetik dönüştürmeleri gerçekleştirmez. Bunun yerine, her işleneni denklik değerini 0 olarak değerlendirirler. Mantıksal işlemin sonucu 0 veya 1 ' dir. Sonucun türü **`int`** .

C mantıksal işleçleri aşağıda açıklanmıştır:

|İşleç|Açıklama|
|--------------|-----------------|
|**&&**|Her iki işlenen de sıfır dışında değerler içeriyorsa, mantıksal AND işleci 1 değerini üretir. Her iki işlenen de 0 ' a eşitse, sonuç 0 ' dır. Mantıksal ve işlemin ilk işleneni 0 ' a eşitse, ikinci işlenen değerlendirilmez.|
|**&#124;&#124;**|Mantıksal OR işleci, işlenenleri üzerinde bir kapsamlı veya işlem gerçekleştirir. Her iki işlenen de 0 değeri varsa sonuç 0 ' dır. İki işlenenin sıfır dışında bir değeri varsa sonuç 1 olur. Bir mantıksal veya işlemin ilk işleneninin sıfır dışında bir değeri varsa, ikinci işlenen değerlendirilmez.|

Mantıksal AND ve mantıksal OR ifadelerinin işlenenleri soldan sağa değerlendirilir. Eğer ilk işlenenin değeri işlemin sonucunu belirleyebilmek için yeterliyse ikinci işlenen değerlendirilmez. Bu, "kısa devre değerlendirmesi" olarak adlandırılır. İlk işlenenden sonra bir sıra noktası var. Daha fazla bilgi için bkz. [dizi noktaları](../c-language/c-sequence-points.md) .

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde mantıksal işleçler gösterilmektedir:

```C
int w, x, y, z;

if ( x < y && y < z )
    printf( "x is less than z\n" );
```

Bu örnekte, **printf** işlevi bir iletiyi yazdırmak için çağrılır ve küçüktür ise küçüktür `x` ve küçüktür olur `y` `y` `z` . `x`Değerinden büyükse `y` , ikinci işlenen ( `y < z` ) değerlendirilmez ve hiçbir şey yazdırılmaz. Bu, ikinci işlenenin başka bir nedenden dolayı güvenmekte olan yan etkileri olduğu durumlarda sorun oluşmasına neden olabileceğini unutmayın.

```C
printf( "%d" , (x == w || x == y || x == z) );
```

Bu örnekte,, `x` ya da öğesine eşitse, `w` `y` `z` **printf** işlevinin ikinci bağımsız değişkeni true olarak değerlendirilir ve 1 değeri yazdırılır. Aksi takdirde, false olarak değerlendirilir ve 0 değeri yazdırılır. Koşullardan biri doğru olarak değerlendirildiğinde değerlendirme sona erer.

## <a name="see-also"></a>Ayrıca bkz.

- [Mantıksal AND İşleci: &&](../cpp/logical-and-operator-amp-amp.md)
- [Mantıksal OR Işleci:  &#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)

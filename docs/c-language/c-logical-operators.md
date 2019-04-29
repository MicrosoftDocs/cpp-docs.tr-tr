---
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
ms.openlocfilehash: 5df0c0f16bdf298c47a6a0699ec10c7392ab84ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326592"
---
# <a name="c-logical-operators"></a>C mantıksal işleçleri

Mantıksal işleçler mantıksal gerçekleştirmek- ve (**&&**) ve mantıksal OR (**||**) işlemleri.

## <a name="syntax"></a>Sözdizimi

*mantıksal-ve-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*OR ifadesi dahil*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal-ve-expression***&&***OR ifadesi dahil*

*mantıksal-veya-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal-ve-ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*logical-OR-expression*  **&#124;&#124;**  *logical-AND-expression*

## <a name="remarks"></a>Açıklamalar

Mantıksal işleçler olağan aritmetik dönüştürmeler yapmayın. Bunun yerine, her işlenen, denklik 0 bakımından değerlendirin. Mantıksal bir işlemin sonucunu, 0 veya 1 ' dir. Sonucunun türü **int**.

C mantıksal işleçleri aşağıda açıklanmıştır:

|İşleç|Açıklama|
|--------------|-----------------|
|**&&**|Mantıksal- ve işleci, her iki işlenen de sıfır olmayan değerler varsa 1 değerini üretir. İki işlenenden 0'a eşit ise, sonuç 0'dır. Varsa bir mantıksal ilk işleneni- ve 0'a eşit işlemi, ikinci işlenenin değerlendirilmez.|
|**&#124;&#124;**|Mantıksal OR işlecine işlenenleri bir düzeyinde kapsamalı OR işlemi gerçekleştirir. Her iki işlenen de 0 değerlere sahip sonucu 0'dır. İki işlenenden sıfır olmayan bir değere sahipse, sonuç 1'dir. Mantıksal OR işleminin ilk işlenen sıfır dışında bir değeri varsa, ikinci işlenenin değerlendirilmez.|

İşlenen mantıksal- ve ve mantıksal OR ifadeleri soldan sağa doğru değerlendirilir. Birinci işlenenin değerini işleminin sonucu belirlemek yeterli ise, ikinci işlenenin değerlendirilmez. Buna "kısa devre değerlendirmesi." adı verilir Sonra ilk işleneni bir dizi noktası yoktur. Bkz: [dizi noktaları](../c-language/c-sequence-points.md) daha fazla bilgi için.

## <a name="examples"></a>Örnekler

Aşağıdaki örnekler, mantıksal işleçlerini gösterir:

```C
int w, x, y, z;

if ( x < y && y < z )
    printf( "x is less than z\n" );
```

Bu örnekte, **printf** çağrıldığında, iletiyi yazdırmak için `x` olduğu küçüktür `y` ve `y` olduğu küçüktür `z`. Varsa `x` büyüktür `y`, ikinci işlenenin (`y < z`) değerlendirilmez ve herhangi bir şey yazdırılmaz. Bu ikinci işlenenin başka bir nedenle yararlandı yan etkileri olduğu durumlarda sorunlara neden olabileceğini unutmayın.

```C
printf( "%d" , (x == w || x == y || x == z) );
```

Bu örnekte, `x` ya da eşittir `w`, `y`, veya `z`, ikinci bağımsız değişkeni **printf** işlevi doğru olarak değerlendirilir ve 1 değeri yazdırılır. Aksi takdirde yanlış değerini ve 0 değeri yazdırılır. Bir koşulun true olarak değerlendirilen hemen sonra değerlendirme olmaktan çıkar.

## <a name="see-also"></a>Ayrıca bkz.

- [Mantıksal AND İşleci: &&](../cpp/logical-and-operator-amp-amp.md)
- [Mantıksal OR işleci:&#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)

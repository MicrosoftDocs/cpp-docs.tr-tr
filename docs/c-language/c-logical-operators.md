---
title: C mantıksal işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f92adbeab4175178be8f41a09c4455d8a581131
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-logical-operators"></a>C Mantıksal İşleçleri
Mantıksal işleçler mantıksal gerçekleştirmek- ve (**&&**) ve mantıksal OR ( `||` ) işlemleri.  
  
 **Sözdizimi**  
  
 *mantıksal-ve-ifadesi*:  
 *OR ifadesi (bunlar dahil)*  
  
 *mantıksal-ve-ifadesi***&&***veya ifadesi (bunlar dahil)*   
  
 *OR ifadesi mantıksal*:  
 *mantıksal-ve-ifadesi*  
  
 *OR ifadesi mantıksal***&#124;&#124;***mantıksal-ve-ifadesi*   
  
 Mantıksal işleçler olağan aritmetik dönüştürmeler gerçekleştirmeyin. Bunun yerine, her işleneni, eşdeğer 0 bakımından değerlendirin. Mantıksal bir işlemin sonucunu, 0 veya 1 ' dir. Sonucunun türü `int`.  
  
 C mantıksal işleçleri aşağıda açıklanmıştır:  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|**&&**|Mantıksal- ve her iki işlenen sıfır olmayan değerler varsa 1 değerini işleci üretir. Her iki işlenen 0'a eşit ise, sonuç 0'dır. Bir mantıksal ilk işleneninin- ve işlem 0'a eşit ise, ikinci işlenen değerlendirilmez.|  
|`&#124;&#124;`|Mantıksal OR işleci işlenenleri üzerinde bir kapsayıcı veya işlemi gerçekleştirir. Her iki işlenen 0 değerleri varsa sonucu 0'dır. Her iki işlenen sıfır olmayan bir değer varsa, sonuç 1'dir. Mantıksal OR işleminin ilk işlenen sıfır olmayan bir değer varsa, ikinci işlenen değerlendirilmez.|  
  
 Mantıksal işlenenleri- ve ve mantıksal OR ifadeler soldan sağa değerlendirilir. İlk işlenen değeri işlemin sonucunu belirlemek yeterliyse ikinci işlenen değerlendirilmez. Bu "değerlendirmesi." olarak adlandırılır Sonra ilk işleneni bir dizi noktası yoktur. Bkz: [sıralama noktaları](../c-language/c-sequence-points.md) daha fazla bilgi için.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örneklerde mantıksal işleçler gösterilmektedir:  
  
```  
int w, x, y, z;  
  
if ( x < y && y < z )  
    printf( "x is less than z\n" );  
```  
  
 Bu örnekte, `printf` çağrıldığında bir ileti yazdırmak için `x` olan değerinden `y` ve `y` olan değerinden `z`. Varsa `x` değerinden daha büyük `y`, ikinci işlenen (`y < z`) değerlendirilmez ve hiçbir şey yazdırılır. Bu ikinci işlenen üzerinde başka bir nedenle dayanıyordu yan etkileri sahip olduğu durumlarda sorunlara neden olabilecek unutmayın.  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 Bu örnekte, `x` ya da eşit olan `w`, `y`, veya `z`, ikinci bağımsız değişkeni `printf` işlevi true olarak değerlendirilir ve değerin 1 yazdırılır. Aksi takdirde yanlış olarak değerlendirilir ve değerin 0 yazdırılır. Koşullardan biri doğru olarak değerlendirir hemen değerlendirme'ü sona erer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mantıksal AND işleci: & &](../cpp/logical-and-operator-amp-amp.md)   
 [Mantıksal OR işleci:&#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)
---
title: Koşullu ifade işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- conditional operators
- operators [C++], conditional
- expressions [C++], conditional
ms.assetid: c4f1a5ca-0844-44a7-a384-eca584d4e3dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f3bead2a40e38698534e433d8e4289eb8da4dc9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386923"
---
# <a name="conditional-expression-operator"></a>Koşullu İfade İşleci
C sahip bir Üçlü işleci: koşullu ifade işleci (**?:**).  
  
## <a name="syntax"></a>Sözdizimi  
 *Koşullu ifade*:  
 *OR ifadesi mantıksal*  
  
 *Mantıksal OR ifadesi***?**   *ifade***:***koşullu ifade*   
  
 *Veya ifadesi mantıksal* Entegral, kayan veya işaretçi türü olmalıdır. 0, eşdeğer açısından değerlendirilir. Bir dizi noktası izleyen *veya ifadesi mantıksal*. İşlenen değerlendirmesi şu şekilde çalışır:  
  
-   Varsa *veya ifadesi mantıksal* 0'a eşit değil *ifade* değerlendirilir. İfade değerlendirme sonucu nonterminal tarafından verilen *ifade*. (Yani *ifade* yalnızca hesaplanan *veya ifadesi mantıksal* geçerlidir.)  
  
-   Varsa *veya ifadesi mantıksal* eşittir 0, *koşullu ifade* değerlendirilir. İfadenin sonucu değeri *koşullu ifade*. (Yani *koşullu ifade* yalnızca hesaplanan *veya ifadesi mantıksal* false olur.)  
  
 Ya da unutmayın *ifade* veya *koşullu ifade* değerlendirilen, ancak ikisi birden değil.  
  
 Türüne göre koşullu bir işlemin sonucunu türüne bağlıdır *ifade* veya *koşullu ifade* şekilde işlenen:  
  
-   Varsa *ifade* veya *koşullu ifade* integral sahip veya olağan aritmetik dönüştürmeler (türlerini olabilir farklı) kayan türünü, işleci gerçekleştirir. Sonuç türü dönüştürmeden sonra işlenen türüdür.  
  
-   Her iki *ifade* ve *koşullu ifade* aynı yapısı, UNION veya işaretçi türü, sonuç türü aynı yapısı, UNION veya işaretçi türüdür.  
  
-   Her iki işlenen türü varsa `void`, sonuç türüne sahip `void`.  
  
-   Her iki işlenen gösteren bir işaretçidir herhangi türde bir nesne ve diğer işleneni gösteren bir işaretçidir `void`, nesne işaretçisine gösteren bir işaretçi dönüştürülür `void` ve sonucu gösteren bir işaretçidir `void`.  
  
-   Her iki *ifade* veya *koşullu ifade* gösteren bir işaretçidir ve diğer işleneni değeri 0 ' sonuç türü olan bir sabit ifadesine işaretçi türü değil.  
  
 İşaretçileri türü karşılaştırılmasına niteleyicileri yazın (**const** veya `volatile`) türünde hangi işaretçi noktalarıdır Önemsiz, ancak sonuç türü niteleyicileri her iki koşul bileşenlerini devralır.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örnekler koşullu işleç kullanımlarını gösterir:  
  
```  
j = ( i < 0 ) ? ( -i ) : ( i );  
```  
  
 Bu örnek mutlak değeri atar `i` için `j`. Varsa `i` 0'dan küçük `-i` atandığı `j`. Varsa `i` büyük veya 0 olarak eşit `i` atandığı `j`.  
  
```  
void f1( void );  
void f2( void );  
int x;  
int y;  
    .  
    .  
    .  
( x == y ) ? ( f1() ) : ( f2() );  
```  
  
 Bu örnekte, iki işlev `f1` ve `f2`ve iki değişken `x` ve `y`, bildirilir. Daha sonra program iki değişken işlevi aynı değeri varsa `f1` olarak adlandırılır. Aksi takdirde, `f2` olarak adlandırılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koşullu İşleç: ? :](../cpp/conditional-operator-q.md)
---
title: Çok boyutlu Arrays (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arrays [C], multidimensional
- multidimensional arrays
- subscript expressions
ms.assetid: 4ba5c360-1f17-4575-b370-45f62e1f2bc2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25ca58d9818782b51e6c07bb6bb758948adab3ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387970"
---
# <a name="multidimensional-arrays-c"></a>Çok Boyutlu Diziler (C)
Bir alt simge ifadesinde de aşağıdaki gibi birden fazla alt simge olabilir:  
  
```  
  
expression1  
[  
expression2  
] [  
expression3  
]...  
```  
  
 Alt simge ifadeleri soldan sağa ilişkilendirilir. Soldaki alt simge ifadesi * İfade1 ***[*** İfade2 ***]**, ilk olarak değerlendirilir. Eklemelerini sonuçları adresi *İfade1* ve *İfade2* bir işaretçi ifadesi; formları sonra *deyim3* yeni bir form için bu işaretçi ifadesi eklenir son alt simge ifadesi bir vb. eklenene kadar işaretçi ifade. İndirection işleci (**\***) son alt ifade değerlendirildikten sonra bir dizi son işaretçi değeri adresleri (aşağıdaki örneklere bakın) yazın sürece uygulanır.  
  
 Birden çok alt simgeye sahip ifadeler, "çok boyutlu dizilerin" öğelerine başvurur. Çok boyutlu bir dizi, öğeleri dizi olan bir dizidir. Örneğin, üç boyutlu bir dizinin ilk öğesi iki boyutlu bir dizidir.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örneklerde `prop` adlı dizi, her biri `int` değerlerinin 4 ile 6 dizisi olan üç öğeyle bildirilir.  
  
```  
int prop[3][4][6];  
int i, *ip, (*ipp)[6];  
```  
  
 `prop` dizisine yapılan başvuru aşağıdaki gibi görünür:  
  
```  
i = prop[0][0][1];  
```  
  
 Yukarıdaki örnekte, `int`'un ikinci `prop` öğesine nasıl başvurulacağı gösterilmektedir. Diziler satıra göre depolanır, bu nedenle en hızlı son alt simge değişir; `prop[0][0][2]` ifadesi dizinin sonraki (üçüncü) öğesine başvurur ve bu düzen böyle devam eder.  
  
```  
i = prop[2][1][3];  
```  
  
 Bu deyim, `prop`'un öğesine yapılan daha karmaşık bir başvurudur. İfade, aşağıdaki gibi değerlendirilir:  
  
1.  İlk alt simge `2`, 4 ile 6 `int` dizisi ile çarpılır ve `prop` işaretçi değerine eklenir. Sonuç, üçüncü 4 ile 6 `prop`'a işaret eder.  
  
2.  İkinci alt simge `1`, 6 öğeli `int` dizisinin boyutuyla çarpılır ve `prop[2]` tarafından temsil edilen adrese eklenir.  
  
3.  6 öğeli dizinin her öğesi bir `int` değeridir, bu nedenle son alt simge `3`, `int` öğesine eklenmeden önce `prop[2][1]` boyutu ile çarpılır. Elde edilen işaretçi, 6 öğeli dizinin dördüncü öğesine yöneliktir.  
  
4.  Yöneltme yol işleci işaretçi değerine uygulanır. Sonuç, bu adresteki `int` öğesidir.  
  
 Bu sonraki iki örnek, yöneltme işlecinin uygulanmadığı durumları gösterir.  
  
```  
ip = prop[2][1];  
  
ipp = prop[2];  
```  
  
 Bu deyimlerin ilkinde, `prop[2][1]` ifadesi üç boyutlu `prop` dizisinin geçerli bir başvurusudur; 6 öğeli bir diziye (yukarıda bildirilmiştir) başvurur. İşaretçi değeri bir diziye yönelik olduğu için yöneltme işleci uygulanmaz.  
  
 Benzer şekilde, ikinci `prop[2]` deyimindeki `ipp = prop[2];` ifadesinin sonucu, iki boyutlu diziye yönelik olan bir işaretçi değeridir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alt Simge İşleci:](../cpp/subscript-operator.md)
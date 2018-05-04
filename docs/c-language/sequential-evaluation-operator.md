---
title: Sıralı değerlendirme işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], sequential-evaluation
- sequential-evaluation operator
- comma operator
ms.assetid: 587514f4-c8e2-44e9-81a8-7a553ce1453a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ed58e141dd811d95fe43ed2d587a2de17b3d656
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="sequential-evaluation-operator"></a>Sıralı Değerlendirme İşleci
"Virgül işleci," olarak da adlandırılan sıralı değerlendirme işleci iki işlenenleri sırayla soldan sağa değerlendirir.  
  
## <a name="syntax"></a>Sözdizimi  
 *ifade*:  
 *atama ifadesi*  
  
 *ifade***,***atama ifadesi*   
  
 Sıralı değerlendirme işleci sol işleneni olarak değerlendirilir bir `void` ifade. İşleminin sonucu sağ işleneni aynı değeri ve türü vardır. Her işlenen herhangi bir türde olabilir. Sıralı değerlendirme işleci işlenenleri arasındaki tür dönüşümleri gerçekleştirmez ve l-değeri vermez. Sağ işleneni değerlendirmesine başlamadan önce tüm yan etkileri sol işleneni değerlendirme tamamlandığı anlamına gelir ilk işlenen sonra bir dizi noktası yoktur. Bkz: [sıralama noktaları](../c-language/c-sequence-points.md) daha fazla bilgi için.  
  
 Sıralı değerlendirme işleci genellikle iki veya daha fazla ifade bağlamlarında değerlendirmek için burada yalnızca bir ifadeye izin kullanılır.  
  
 Bazı bağlamlarda ayırıcı olarak virgül kullanılabilir. Ancak, kullanımı virgül ayırıcı olarak ile bir işleç olarak kullanılmasını karıştırır değil dikkatli olmanız gerekir; tamamen farklı iki kullanır.  
  
## <a name="example"></a>Örnek  
 Bu örnekte sıralı değerlendirme işleci gösterilmektedir:  
  
```  
for ( i = j = 1; i + j < 20; i += i, j-- );  
```  
  
 Bu örnekte, her işleneni **için** deyiminin üçüncü ifade bağımsız olarak değerlendirilir. Sol işleneni `i += i` değerlendirilen ilk; sağ işleneni olduğundan `j--`, değerlendirilir.  
  
```  
func_one( x, y + 2, z );  
func_two( (x--, y + 2), z );  
```  
  
 İşlev çağrısı için `func_one`, virgülle ayırarak üç bağımsız değişken geçirilir: `x`, `y + 2`, ve `z`. `func_two` işlev çağrısında, parantezler derleyiciyi, ilk virgülü sıralı değerlendirme işleci olarak yorumlamaya zorlar. Bu işlev çağrısı, `func_two` öğesine iki bağımsız değişken geçirir. İlk bağımsız değişken, `(x--, y + 2)` ifadesinin değerine ve türüne sahip olan `y + 2` sıralı değerlendirme işleminin sonucudur; ikinci bağımsız değişken ise `z`'dir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Virgül İşleci: ,](../cpp/comma-operator.md)
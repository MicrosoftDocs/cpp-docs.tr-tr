---
title: Öncelik ve değerlendirme sırası | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- associativity of operators [C++]
- precedence [C++], operators
- data binding [C++], operator precedence
- operators [C++], precedence
ms.assetid: 201f7864-0c51-4c55-9d6f-39c5d013bcb0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca8f77ee6d49aede8592d591241f8e2730fc15a8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218462"
---
# <a name="precedence-and-order-of-evaluation"></a>Öncelik ve Değerlendirme Sırası
C işleçlerinin öncelik ve birleşimleri, ifadelerde işlenenlerin gruplandırılmasını ve değerlendirilmesini etkiler. Bir işlecin önceliği, daha yüksek veya daha düşük önceliğe sahip başka işleçler varsa bir anlam ifade eder. Önce daha yüksek önceliğe sahip işleçler değerlendirilir. Öncelik, "bağlama" sözcüğüyle de açıklanabilir. Daha yüksek önceliğe sahip işleçlerin daha sıkı bağlamaya sahip olduğu söylenir.  
  
 Aşağıdaki tabloda, C işleçlerinin öncelik ve ilişkilendirilebilirliği (işlenenlerin değerlendirilme sırası) özetlenmekte ve öncelikleri en yüksekten en düşüğe listelenmektedir. Birkaç işlecin birlikte göründüğü yerlerde, bu işleçler aynı önceliğe sahip olur ve ilişkilendirilebilirliklerine göre değerlendirilir. Tablodaki işleçleri ile başlayan bölümlerde açıklanmıştır [sonek işleçleri](../c-language/postfix-operators.md). Bu bölümün geri kalanında, öncelik ve ilişkilendirilebilirlik hakkında genel bilgiler verilmektedir.  
  
## <a name="precedence-and-associativity-of-c-operators"></a>C İşleçlerinin Önceliği ve İlişkilendirilebilirliği  
  
|Sembol <sup>1</sup>|İşlem Türü|İlişkilendirilebilirlik|  
|-------------|-----------------------|-------------------|  
|**\[ ] ( ) . ->**<br /><br />**++** **--** (sonek)|İfade|Soldan sağa|  
**sizeof & \* + - ~!**<br /><br />**++--** (ön ek)|Birli|Sağdan sola|  
|*yuvarlamasını*|Birli|Sağdan sola|  
|**\* / %**|Çarpma|Soldan sağa|  
|**+ -**|Eklenebilir|Soldan sağa|  
|**\<\< >>**|Bit düzeyinde kaydırma|Soldan sağa|  
|**\< > \<= >=**|İlişkisel|Soldan sağa|  
|**== !=**|Eşitlik|Soldan sağa|  
|**&**|Bit düzeyinde AND|Soldan sağa|  
|**^**|Bit düzeyinde dışlamalı OR|Soldan sağa|  
|**&#124;**|Bit düzeyinde kapsamalı OR|Soldan sağa|  
|**&&**|Mantıksal AND|Soldan sağa|  
|**&#124;&#124;**|Mantıksal OR|Soldan sağa|  
|**? :**|Koşullu ifade|Sağdan sola|  
|**= \*= /= %=**<br /><br /> **+= -= \<\<= >>= &=**<br /><br /> **^= &#124;=**|Basit ve bileşik atama <sup>2</sup>|Sağdan sola|  
|**,**|Sıralı değerlendirme|Soldan sağa|  
  
 1. İşleçler, öncelik sırasına göre azalan olarak listelenmiştir. Aynı satırda veya grupta birkaç işleç görünüyorsa, bunlar eşit önceliğe sahip olur.  
  
 2. Tüm basit ve bileşik atama işleçleri eşit önceliğe sahiptir.  
  
 Bir ifade eşit önceliğe sahip birkaç işleç içerebilir. Böyle birkaç işleç bir ifadede aynı düzeyde göründüğünde, değerlendirme işlecin ilişkilendirilebilirliğine göre sağdan sola veya soldan sağa devam eder. Değerlendirmenin yönü, birden fazla çarpma içeren ifadelerin sonuçlarını etkilemez (<strong>\*</strong>), toplama (**+**), veya ikili bit düzeyinde (**&**, **&#124;**, veya **^**) aynı düzeyde işleci. İşlemlerin sırası dil tarafından tanımlanmaz. Derleyici, tutarlı bir sonuç sağladığı sürece bu tür ifadeleri herhangi bir sırada değerlendirebilir.  
  
 Yalnızca sıralı değerlendirme (**,**), mantıksal- ve (**&&**), mantıksal OR (**||**), koşullu ifade (**?:** ), ve işleç çağrısı işleçleri dizi noktaları oluşturur ve bu nedenle değerlendirme işlenenleri için belirli bir sıraya garanti. İşlev çağrısı işleci, işlev tanımlayıcısının arkasından gelen bir parantezler kümesidir. Sıralı değerlendirme işleci (**,**), işlenenlerini soldan sağa değerlendirmesi garanti edilir. (Bir işlev çağrısındaki virgül işlecinin sıralı değerlendirme işleciyle aynı olmadığını ve böyle bir garanti vermediğini unutmayın.) Daha fazla bilgi için [dizi noktaları](../c-language/c-sequence-points.md).  
  
 Mantıksal işleçler de işlenenlerinin soldan sağa değerlendirilmesini garanti eder. Bununla birlikte, ifadenin sonucunu belirlemek için gereken en az sayıda işleneni değerlendirirler. Buna "kısa devre" değerlendirmesi adı verilir. Bu nedenle, ifadenin bazı işlenenleri değerlendirilmeyebilir. Örneğin, ifadede  
  
`x && y++`  
  
 ikinci işlenen `y++`, yalnızca `x` true (sıfırdan farklı) olduğunda değerlendirilir. Bu nedenle, `y``x` yanlış (0) olduğunda artmaz.  
  
## <a name="examples"></a>Örnekler
  
 Aşağıdaki listede, derleyicinin bazı örnek ifadeleri otomatik olarak nasıl bağladığı gösterilmektedir:  

|İfade|Otomatik Bağlama|  
|----------------|-----------------------|  
|bir & b &#124; &#124; c|(bir & b). &#124; &#124; c|  
|bir = b &#124; &#124; c|bir = (b &#124; &#124; c).|  
|q & & r &#124; &#124; s--|(q & & r) &#124; &#124; s--|  

 İlk ifadede, bit düzeyinde- ve işleci (**&**) mantıksal OR işlecine daha yüksek bir önceliğe sahiptir (**||**), bu nedenle `a & b` ilk işleneni formlar Mantıksal OR işlemi.  
  
 İkinci ifadede, mantıksal OR işleci (**||**) basit atama işleci daha yüksek bir önceliğe sahiptir (**=**), bu nedenle `b || c` olarak gruplandırılır sağ işlenen olarak. `a`'ya atanan değerin 0 veya 1 olduğuna dikkat edin.  
  
 Üçüncü ifade, beklenmedik bir sonuç oluşturabilecek doğru bir şekilde biçimlendirilmiş bir ifadeyi gösterir. Mantıksal- ve işleci (**&&**) mantıksal OR işlecine daha yüksek bir önceliğe sahiptir (**||**), bu nedenle `q && r` bir işlenen olarak gruplandırılır. Mantıksal işleçler işlenenlerin soldan sağa doğru garanti olduğundan `q && r` önce değerlendirilir `s--`. Ancak, varsa `q && r` sıfır olmayan bir değer olarak değerlendirilirse `s--` değerlendirilmez ve `s` azaltılmaz. Azaltma değil, `s` bir sorun, programınızda neden `s--` ifade ilk işleneni görünmesi gereken veya `s` ayrı bir işlemde indirildiği olmalıdır.  
  
 Aşağıdaki ifade geçersizdir ve derleme zamanında bir tanılama iletisi oluşturur:  
  
|Geçersiz İfade|Varsayılan Gruplandırma|  
|------------------------|----------------------|  
|p == 0? p += 1: p += 2|(p == 0? p += 1: p) += 2|  
  
 Bu ifadede, eşitlik işleci (**==**) en yüksek önceliğe serileştirilmesini `p == 0` bir işlenen olarak gruplandırılır. Koşullu ifade işleci (**?:**) sonraki en yüksek önceliğe sahiptir. İlk işleneni `p == 0`, ikinci işleneni ise `p += 1`'dir. Ancak, koşullu ifade işlecinin son işleneni `p` yerine `p += 2` olarak kabul edilir; çünkü bu `p` örneği koşullu ifade işlecine, bileşik atama işlecine göre daha yakından bağlanır. `+= 2` sol işlenene sahip olmadığı için bir sözdizimi hatası oluşur. Bu türden hataları önlemek ve daha okunabilir bir kod oluşturmak için parantez kullanmanız gerekir. Örneğin, yukarıdaki örneği düzeltmek ve netleştirmek için parantezleri aşağıda gösterildiği gibi kullanabilirsiniz:  
  
`( p == 0 ) ? ( p += 1 ) : ( p += 2 )`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C İşleçleri](../c-language/c-operators.md)

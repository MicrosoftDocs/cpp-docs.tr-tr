---
title: "C ilişkisel ve eşitlik işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- relational operators, syntax
- equality operator
- operators [C], equality
- equality operator, syntax
- operators [C], relational
ms.assetid: c89a3815-a65e-4e0d-8333-0e8dc7fdb30b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6860198b9acce372b710e819a17f534e793f1ead
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-relational-and-equality-operators"></a>C İlişkisel ve Eşitlik İşleçleri
Belirtilen ilişki geçerliliğini sınamak için ikinci işlenen kendi ilk işlenen ikili ilişkisel ve eşitlik işleçleri karşılaştırın. Sınanan ilişki true ve 0 ise false ise ilişkisel bir ifadenin sonucu 1'dir. Sonuç türü olan `int`.  
  
 **Sözdizimi**  
  
 *ifade ilişkisel*:  
 *Shift ifade*  
  
 *ifade ilişkisel***\<***shift ifade*   
  
 *ifade ilişkisel***>***shift ifade*   
  
 *ifade ilişkisel***\<=***shift ifade*   
  
 *ifade ilişkisel***>=***shift ifade*   
  
 *Eşitlik ifade*:  
 *ifade ilişkisel*  
  
 *Eşitlik ifade***==***ifade ilişkisel*   
  
 *Eşitlik ifade***! =***ifade ilişkisel*   
  
 İlişkisel ve eşitlik işleçleri aşağıdaki ilişkileri test edin:  
  
|İşleç|Test ilişkisi|  
|--------------|-------------------------|  
|**\<**|İkinci işlenen'den küçük ilk işlenen|  
|**>**|İlk işlenen ikinci işlenen büyük|  
|**\<=**|İlk işlenen daha az veya bu değere eşit ikinci işlenen|  
|**>=**|İlk işlenen ikinci işlenen eşit veya daha büyük|  
|`==`|İlk işlenen ikinci işlenen eşit|  
|`!=`|İlk işlenen ikinci işlenen eşit değil|  
  
 Yukarıdaki listede ilk dört operatörleri eşitlik işleçleri daha yüksek önceliğe sahiptir (`==` ve `!=`). Tablodaki öncelik bilgi [öncelik ve C işleçleri birleşim](../c-language/precedence-and-order-of-evaluation.md).  
  
 İşlenen integral, kayan veya işaretçi türü olabilir. İşlenen türleri farklı olabilir. İlişkisel işleçler olağan aritmetik dönüştürmeler Entegral ve kayan türü işlenen üzerinde gerçekleştirin. Ayrıca, işlenen türleri ile ilişkisel ve eşitlik işleçleri aşağıdaki birleşimlerini kullanabilirsiniz:  
  
-   Her ilişkisel işlenenleri veya eşitlik işleci aynı türü işaretçileri olabilir. Eşitlik için (`==`) ve eşitsizlik (`!=`) işleçleri, karşılaştırma sonucunu gösteren iki işaretçileri aynı bellek konumuna yönelik olup olmadığını. Bir ilişkisel işleçleri (**\<**,  **>** ,  **\<** = ve  **>** =), Karşılaştırmanın sonucu işaret nesnelerinin iki bellek adresleri göreli konumunu gösterir. İlişkisel işleçler yalnızca uzaklıkları karşılaştırın.  
  
     İşaretçi karşılaştırması yalnızca aynı nesne bölümleri için tanımlanır. İşaretçiler bir dizi üyelerine başvurursanız, karşılık gelen alt simgeler bir karşılaştırması için karşılaştırma eşdeğerdir. İlk dizi öğesi adresidir "den" son öğe adresidir. Yapıları söz konusu olduğunda, daha sonra bildirilen yapısı üye işaretçileri yapısı içinde bildirilen üyeleri için "büyüktür" işaretçiler ' dir. Aynı birleşim üyeleri işaretçileri eşit.  
  
-   İşaretçi değeri sabit değer 0 eşitlik için karşılaştırılabilir (`==`) veya eşitsizlik (`!=`). Bir işaretçi değeri 0 olan bir "null" işaretçi çağrılır; diğer bir deyişle, geçerli bellek konumuna işaret etmiyor.  
  
-   Eşitlik işleçleri ilişkisel işleçleri olarak aynı kuralları izleyin, ancak ek olanaklar izin: bir işaretçi değeri 0 ile sabit bir tamsayı ifade ya da bir işaretçi karşılaştırılabilir `void`. İki işaretçileri hem null işaretçiler varsa, bunlar eşit olarak karşılaştırın. Eşitlik işleçleri segment ve uzaklık karşılaştırın.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örnekler ilişkisel göstermek ve eşitlik işleçleri.  
  
```  
int x = 0, y = 0;  
if ( x < y )  
```  
  
 Çünkü `x` ve `y` olan eşit, bu örnek ifadesinde 0 değeri verir.  
  
```  
char array[10];  
char *p;  
  
for ( p = array; p < &array[10]; p++ )  
    *p = '\0';  
```  
  
 Bu örnekte parça her öğeye ayarlar `array` için bir null karakter sabiti.  
  
```  
enum color { red, white, green } col;  
   .  
   .  
   .  
   if ( col == red )  
   .  
   .  
   .  
```  
  
 Bu ifadeler adlı bir numaralandırma değişken bildirin `col` etiketiyle `color`. Herhangi bir zamanda numaralandırması kümenin öğeleri birini temsil eden bir tamsayı değeri 0, 1 veya 2, değişkeni içerebilir `color`: rengi kırmızı, beyaz veya yeşil, sırasıyla. Varsa `col` 0 içeren zaman **varsa** deyimi yürütüldüğünde, bağlı olarak deyimleri **varsa** yürütülür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İlişkisel işleçler: \<, >, \<= ve > =](../cpp/relational-operators-equal-and-equal.md)   
 [Eşitlik İşleçleri: == ve !=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)
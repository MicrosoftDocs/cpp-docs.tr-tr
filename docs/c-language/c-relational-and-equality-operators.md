---
title: C ilişkisel ve eşitlik işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- relational operators, syntax
- equality operator
- operators [C], equality
- equality operator, syntax
- operators [C], relational
ms.assetid: c89a3815-a65e-4e0d-8333-0e8dc7fdb30b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1bf3c406059fe8744843e1353ad997acc19c499b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058243"
---
# <a name="c-relational-and-equality-operators"></a>C İlişkisel ve Eşitlik İşleçleri

İkili ilişkisel ve eşitlik işleçleri, belirtilen ilişki geçerliliğini sınamak için ikinci işlenen ilk işlenenin karşılaştırın. Test edilen ilişki true ve 0 ise false ise ilişkisel bir ifadenin sonucu 1'dir. Sonuç türü olan `int`.

**Söz dizimi**

*İlişkisel ifade*: *shift-expression*

*İlişkisel ifade***\<***shift-expression* 

*İlişkisel ifade***>***shift-expression* 

*İlişkisel ifade***\<=***shift-expression* 

*İlişkisel ifade***>=***shift-expression* 

*Eşitlik ifade*: *ilişkisel ifade*

*Eşitlik ifade***==***ilişkisel ifade* 

*Eşitlik ifade***! =***ilişkisel ifade* 

İlişkisel ve eşitlik işleçleri aşağıdaki ilişkileri test:

|İşleç|Test ilişkisi|
|--------------|-------------------------|
|**\<**|İkinci işlenenin değerinden ilk işlenenin|
|**>**|Birinci işlenenin ikinci işlenenin büyük|
|**\<=**|İlk işlenenin daha az veya eşit ikinci işlenen|
|**>=**|Birinci işlenenin ikinci işlenen ya da daha büyük|
|`==`|Birinci işlenenin ikinci işlenenin değerine eşit|
|`!=`|Birinci işlenenin ikinci işlenenin değerine eşit değil|

Yukarıdaki listede ilk dört işleçleri eşitlik işleçleri daha yüksek bir önceliğe sahip (`==` ve `!=`). Tabloda öncelik bilgi [önceliği ve ilişkilendirilebilirliği, C işleçleri](../c-language/precedence-and-order-of-evaluation.md).

İşlenen, integral, kayan veya işaretçi türü olabilir. İşlenen türleri farklı olabilir. İlişkisel işleçler olağan aritmetik dönüştürmeler integral ve kayan türü işlenen üzerinde gerçekleştirin. Ayrıca, aşağıdaki birleşimler işlenen türleri ile ilişkisel ve eşitlik işleçleri kullanabilirsiniz:

- Her iki işleneni de her ilişkisel veya eşitlik işleci aynı türü işaretçileri olabilir. Eşitlik (`==`) ve eşitsizlik (`!=`) işleçleri, Karşılaştırmanın sonucu gösterir iki işaretçi aynı bellek konumunda adresi olup olmadığını. Bir ilişkisel işleçleri (**\<**, **>**, **\<**=, ve **>**=), Karşılaştırmanın sonucu işaret edilen nesne iki bellek adresleri göreli konumunu belirtir. İlişkisel işleçler yalnızca uzaklıkları karşılaştırın.

     İşaretçi karşılaştırması, yalnızca aynı nesneye bölümleri için tanımlanır. Bir dizi üyeleri için işaretçiler başvuruda bulunursanız, karşılık gelen alt simgeleri, karşılaştırma karşılaştırma eşdeğerdir. İlk dizi öğesinin adresidir "değerinden" son öğenin adresi. Söz konusu olduğunda, daha sonra bildirilen Yapı üyeleri için işaretçiler "büyüktür" yapısı içinde bildirilen üye işaretçileri yapılardır. Aynı union üyelerinin işaretçileri eşit olur.

- Bir işaretçi değeri sabit değerin 0 eşitlik için karşılaştırılabilir (`==`) ve eşitsizlik (`!=`). 0 değeri ile bir işaretçi, "null" bir işaretçi olarak adlandırılır; diğer bir deyişle, geçerli bir bellek konumuna işaret etmiyor.

- Eşitlik işleçleri operatörler aynı kuralları izleyin, ancak ek olasılıklar izin ver: bir işaretçi değeri 0 olan sabit bir tam sayı ifade veya işaretçi karşılaştırılabilir `void`. İki işaretçileri hem null işaretçiyse, bunlar eşit olarak karşılaştırılır. Eşitlik işleçleri segment hem uzaklık karşılaştırın.

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde ilişkisel göstermek ve eşitlik işleçleri.

```
int x = 0, y = 0;
if ( x < y )
```

Çünkü `x` ve `y` olan eşittir ifadesi bu örnekte 0 değeri verir.

```
char array[10];
char *p;

for ( p = array; p < &array[10]; p++ )
    *p = '\0';
```

Bu örnekte parça her öğeye ayarlar `array` boş karakter sabiti için.

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

Bu deyimler adlı bir numaralandırma değişken bildirimini `col` etiketiyle `color`. Herhangi bir zamanda bir numaralandırma kümenin öğelerini temsil eden bir tamsayı değeri 0, 1 veya 2, değişken içerebilir `color`: kırmızı, beyaz veya yeşil, sırasıyla. Varsa `col` 0 içeren zaman **varsa** deyimi yürütüldüğünde, bağlı herhangi bir deyim **varsa** yürütülecek.

## <a name="see-also"></a>Ayrıca Bkz.

[İlişkisel işleçler: \<, >, \<= ve > =](../cpp/relational-operators-equal-and-equal.md)<br/>
[Eşitlik İşleçleri: == ve !=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)
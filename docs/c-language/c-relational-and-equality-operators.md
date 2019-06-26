---
title: C İlişkisel ve Eşitlik İşleçleri
ms.date: 10/18/2018
helpviewer_keywords:
- relational operators, syntax
- equality operator
- operators [C], equality
- equality operator, syntax
- operators [C], relational
ms.assetid: c89a3815-a65e-4e0d-8333-0e8dc7fdb30b
ms.openlocfilehash: 25e9bb65492e0c4b100ecd7a800491d238b1dd38
ms.sourcegitcommit: 8bb2bea1384b290b7570b01608a86c7488ae7a02
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67400524"
---
# <a name="c-relational-and-equality-operators"></a>C İlişkisel ve Eşitlik İşleçleri

İkili ilişkisel ve eşitlik işleçleri, belirtilen ilişki geçerliliğini sınamak için ikinci işlenen ilk işlenenin karşılaştırın. Test edilen ilişki true ve 0 ise false ise ilişkisel bir ifadenin sonucu 1'dir. Sonuç türü olan `int`.

**Söz dizimi**

*İlişkisel ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Shift-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İlişkisel ifade* **&lt;** *shift-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İlişkisel ifade* **>** *shift-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İlişkisel ifade* **&lt; =** *shift-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İlişkisel ifade* **>=** *shift-expression*

*Eşitlik ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*İlişkisel ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Eşitlik ifade* **==** *ilişkisel ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Eşitlik ifade* **! =** *ilişkisel ifade*

İlişkisel ve eşitlik işleçleri aşağıdaki ilişkileri test:

|İşleç|Test ilişkisi|
|--------------|-------------------------|
|**&lt;**|İkinci işlenenin değerinden ilk işlenenin|
|**>**|Birinci işlenenin ikinci işlenenin büyük|
|**&lt;=**|İlk işlenenin daha az veya eşit ikinci işlenen|
|**>=**|Birinci işlenenin ikinci işlenen ya da daha büyük|
|**==**|Birinci işlenenin ikinci işlenenin değerine eşit|
|**\!=**|Birinci işlenenin ikinci işlenenin değerine eşit değil|

Yukarıdaki listede ilk dört işleçleri eşitlik işleçleri daha yüksek bir önceliğe sahip (`==` ve `!=`). Tabloda öncelik bilgi [önceliği ve ilişkilendirilebilirliği, C işleçleri](../c-language/precedence-and-order-of-evaluation.md).

İşlenen, integral, kayan veya işaretçi türü olabilir. İşlenen türleri farklı olabilir. İlişkisel işleçler olağan aritmetik dönüştürmeler integral ve kayan türü işlenen üzerinde gerçekleştirin. Ayrıca, aşağıdaki birleşimler işlenen türleri ile ilişkisel ve eşitlik işleçleri kullanabilirsiniz:

- Her iki işleneni de her ilişkisel veya eşitlik işleci aynı türü işaretçileri olabilir. Eşitlik (`==`) ve eşitsizlik (`!=`) işleçleri, Karşılaştırmanın sonucu gösterir iki işaretçi aynı bellek konumunda adresi olup olmadığını. Bir ilişkisel işleçleri ( **\<** , **>** , **\<** =, ve **>** =), Karşılaştırmanın sonucu işaret edilen nesne iki bellek adresleri göreli konumunu belirtir. İlişkisel işleçler yalnızca uzaklıkları karşılaştırın.

   İşaretçi karşılaştırması, yalnızca aynı nesneye bölümleri için tanımlanır. Bir dizi üyeleri için işaretçiler başvuruda bulunursanız, karşılık gelen alt simgeleri, karşılaştırma karşılaştırma eşdeğerdir. İlk dizi öğesinin adresidir "değerinden" son öğenin adresi. Söz konusu olduğunda, daha sonra bildirilen Yapı üyeleri için işaretçiler "büyüktür" yapısı içinde bildirilen üye işaretçileri yapılardır. Aynı union üyelerinin işaretçileri eşit olur.

- Bir işaretçi değeri sabit değerin 0 eşitlik için karşılaştırılabilir (`==`) ve eşitsizlik (`!=`). 0 değeri ile bir işaretçi, "null" bir işaretçi olarak adlandırılır; diğer bir deyişle, geçerli bir bellek konumuna işaret etmiyor.

- Eşitlik işleçleri operatörler aynı kuralları izleyin, ancak ek olasılıklar izin ver: bir işaretçi değeri 0 olan sabit bir tam sayı ifade veya işaretçi karşılaştırılabilir `void`. İki işaretçileri hem null işaretçiyse, bunlar eşit olarak karşılaştırılır. Eşitlik işleçleri segment hem uzaklık karşılaştırın.

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde ilişkisel göstermek ve eşitlik işleçleri.

```C
int x = 0, y = 0;
if ( x < y )
```

Çünkü `x` ve `y` olan eşittir ifadesi bu örnekte 0 değeri verir.

```C
char array[10];
char *p;

for ( p = array; p < &array[10]; p++ )
    *p = '\0';
```

Bu örnekte parça her öğeye ayarlar `array` boş karakter sabiti için.

```C
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

## <a name="see-also"></a>Ayrıca bkz.

[İlişkisel işleçler: \<, >, \<= ve > =](../cpp/relational-operators-equal-and-equal.md)<br/>
[Eşitlik İşleçleri: == ve !=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)

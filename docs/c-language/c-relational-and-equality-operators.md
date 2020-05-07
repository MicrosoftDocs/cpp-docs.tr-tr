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

İkili ilişkisel ve eşitlik işleçleri, belirtilen ilişkinin geçerliliğini test etmek için ilk işlenenlerini ikinci işlenenden karşılaştırın. Bir ilişkisel ifadenin sonucu, sınanan ilişki true ise 1, yanlışsa 0 olur. Sonucun türü `int`.

**Sözdizimi**

*ilişkisel ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*SHIFT ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ilişkisel-ifade* **&lt;** *kaydırma ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ilişkisel-ifade* **>** *kaydırma ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ilişkisel-ifade* ** &lt; ** *kaydırma ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ilişkisel-ifade* **>=** *kaydırma ifadesi*

*eşitlik ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ilişkisel ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eşitlik-ifade* **==** *ilişkisel ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*eşitlik-ifade* **! =** *ilişkisel-ifade*

İlişkisel ve eşitlik işleçleri aşağıdaki ilişkileri test edin:

|İşleç|İlişki test edildi|
|--------------|-------------------------|
|**&lt;**|Birinci işlenen ikinci işlenenin küçüktür|
|**>**|İkinci işleneni aşan ilk işlenen|
|**&lt;=**|İlk işlenen ikinci işlenenden küçük veya eşit|
|**>=**|İlk işlenen ikinci işlenenden büyük veya eşit|
|**==**|İlk işlenen ikinci işlenenin değerine eşit|
|**!=**|Birinci işlenen ikinci işlenene eşit değil|

Yukarıdaki listede ilk dört işlecin eşitlik işleçlerinden (`==` ve `!=`) daha yüksek önceliği vardır. [C işleçleri için tablo önceliği ve Ilişkilendirilebilirliği](../c-language/precedence-and-order-of-evaluation.md)içindeki öncelik bilgilerine bakın.

İşlenenler integral, kayan veya işaretçi türüne sahip olabilir. İşlenen türleri farklı olabilir. İlişkisel işleçler, integral ve kayan tür işlenenlerinde her zamanki aritmetik dönüştürmeleri gerçekleştirir. Buna ek olarak, ilişkisel ve eşitlik işleçleri ile aşağıdaki işlenen türleri birleşimlerini kullanabilirsiniz:

- Herhangi bir ilişkisel ya da eşitlik işlecinin her iki işleneni de aynı türde işaretçiler olabilir. Eşitlik (`==`) ve eşitsizlik (`!=`) işleçleri için, karşılaştırma sonucu iki işaretçinin aynı bellek konumuna erişip erişemeyeceğini belirtir. Diğer ilişkisel işleçler**\<**(, **>**, **\<**= ve **>**=) için, karşılaştırma sonucu, işaret edilen nesnelerin iki bellek adreslerinin göreli konumunu gösterir. İlişkisel işleçler yalnızca uzaklıkları Karşılaştır.

   İşaretçi karşılaştırması yalnızca aynı nesnenin bölümleri için tanımlanır. İşaretçiler bir dizinin üyelerine başvurursanız, karşılaştırma karşılık gelen alt simgelerin karşılaştırmasına eşdeğerdir. İlk dizi öğesinin adresi, son öğenin adresinden "küçüktür" dır. Yapılar söz konusu olduğunda, daha sonra bildirildiği yapı üyelerine yönelik işaretçiler, yapıda daha önce belirtilen üyelerin "büyüktür" işaretçileridir. Aynı birleşimin üyelerine yönelik işaretçiler eşittir.

- Bir işaretçi değeri, eşitlik (`==`) veya eşitsizlik (`!=`) için 0 sabit değeriyle karşılaştırılabilir. 0 değerine sahip bir işaretçiye "null" işaretçisi denir; Yani, geçerli bir bellek konumunu işaret etmez.

- Eşitlik işleçleri, ilişkisel işleçlerle aynı kurallara uyar, ancak ek olasılıklara izin verir: bir işaretçi 0 değeri olan bir sabit integral ifadesiyle veya bir işaretçiyle karşılaştırılabilir `void`. İki işaretçinin ikisi de null işaretçilerdir, eşit olarak karşılaştırırlar. Eşitlik işleçleri hem segmenti hem de sapmayı karşılaştırır.

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde ilişkisel ve eşitlik işleçleri gösterilmektedir.

```C
int x = 0, y = 0;
if ( x < y )
```

Ve `x` `y` eşit olduğu için, bu örnekteki ifade 0 değerini verir.

```C
char array[10];
char *p;

for ( p = array; p < &array[10]; p++ )
    *p = '\0';
```

Bu örnekteki parça her öğesini `array` bir null karakter sabitine ayarlar.

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

Bu deyimler etiketiyle `col` `color`adlı bir numaralandırma değişkeni bildirir. Herhangi bir zamanda, değişkeni, numaralandırma kümesinin `color`öğelerinden birini temsil eden 0, 1 veya 2 tamsayı değerini içerebilir: sırasıyla kırmızı, beyaz veya yeşil renk. If `col` deyimi yürütüldüğünde 0 içeriyorsa **if** **, öğesine** bağlı olarak herhangi bir deyim yürütülür.

## <a name="see-also"></a>Ayrıca bkz.

[İlişkisel Işleçler: \<, >, \<= ve >=](../cpp/relational-operators-equal-and-equal.md)<br/>
[Eşitlik İşleçleri: == ve !=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)

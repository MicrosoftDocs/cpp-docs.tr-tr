---
title: Kayan nokta türlerinden dönüşümler
ms.date: 10/02/2019
helpviewer_keywords:
- converting floating point
- floating-point conversion
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
ms.openlocfilehash: 72d0f95a6e48dcf0a5e8fea3757e85f9a03bf7e4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227900"
---
# <a name="conversions-from-floating-point-types"></a>Kayan nokta türlerinden dönüşümler

Diğer kayan nokta türüne dönüştürülen bir kayan nokta değeri, orijinal değerin sonuç türünde tam olarak gösterilebilir olması durumunda değer üzerinde değişiklik yapılmaz. Özgün değer sayısal ise, ancak tam olarak gösterilemeyen, sonuç bir sonraki daha büyük veya daha düşük bir sonraki değer olan değerdir. Kayan nokta türleri aralığı için [kayan nokta sabitleri sınırlarına](../c-language/limits-on-floating-point-constants.md) bakın.

Tamsayı türüne dönüştürülen bir kayan nokta değeri ilk olarak kesirli değer atılarak kesilir. Bu kesilen değer sonuç türünde gösterilebilir ise, sonuç bu değer olmalıdır. Gösterilemeyen bir tablo olmadığında sonuç değeri tanımsızdır.

**Microsoft'a Özgü**

Microsoft derleyicileri değerleri için IEEE-754 binary32 temsili **`float`** ve ve binary64 temsili kullanır **`long double`** **`double`** . **`long double`** **`double`** Aynı gösterimi kullandığından, aynı aralığa ve duyarlığa sahiptir.

Derleyici bir **`double`** veya **`long double`** kayan noktalı sayıyı öğesine dönüştürdüğünde, **`float`** sonucu kayan nokta ortam denetimlerine göre yuvarlar, bu, varsayılan olarak en yakın "en yakına yuvarlanır" olarak yapılır. Sayısal bir değer çok yüksek veya sayısal bir değer olarak gösterilemeyecek kadar düşükse **`float`** , dönüştürme sonucu özgün değerin işaretine göre pozitif veya negatif sonsuzluk olur ve etkinleştirilirse bir taşma özel durumu oluşturulur.

Tamsayı türlerine dönüştürürken, ' den küçük bir türe dönüştürmenin sonucu **`long`** değerin değerine dönüştürülmesi **`long`** ve sonra sonuç türüne dönüştürülmesi sonucu olur.

Tamsayı türlerine en az büyük ölçüde dönüştürmek için **`long`** , sonuç türünde temsil etmek için çok yüksek veya çok düşük bir değer dönüştürmesi aşağıdaki değerlerden herhangi birini döndürebilir:

- Sonuç, sıfırdan en uzak gösterilemeyen bir değer olan *Sentinel değeri*olabilir. İmzalı türler için en düşük gösterilebilir tablo değeridir (0x800... 0). İmzasız türler için en yüksek gösterilebilir tablo değeridir (0xFF... F).

- Sonuç, değerlerin temsil edildiği çok yüksek değeri en yüksek gösterilemeyen değere dönüştürüldüğü ve temsil etmek için çok düşük değerler en düşük gösterilemeyen değere dönüştürülerek *doygun*olabilir. Bu iki değerden biri Sentinel değeri olarak da kullanılır.

- Veya ' a dönüştürme için **`unsigned long`** **`unsigned long long`** , Aralık dışı bir değeri dönüştürmenin sonucu, en yüksek veya en düşük gösterilemeyen değer dışında bir değer olabilir. Sonucun Sentinel veya doygun bir değer olup olmadığı veya derleyicinin seçeneklerine ve hedef mimarisine bağlı olup olmadığı. Gelecekteki derleyici yayınları, bunun yerine bir doygun veya Sentinel değeri döndürebilir.

**SON Microsoft 'a özgü**

Aşağıdaki tabloda, kayan türlerden dönüşümler özetlenmektedir.

## <a name="table-of-conversions-from-floating-point-types"></a>Kayan nokta türlerinden dönüştürme tablosu

|Kaynak|Amaç|Yöntem|
|----------|--------|------------|
|**`float`**|**`char`**|Dönüştür **`long`** ; Dönüştür **`long`****`char`**|
|**`float`**|**`short`**|Dönüştür **`long`** ; Dönüştür **`long`****`short`**|
|**`float`**|**`int`**|Ondalık noktada kesin. Sonuç, olarak gösterilemeyecek kadar büyükse **`int`** , sonuç tanımsızdır.|
|**`float`**|**`long`**|Ondalık noktada kesin. Sonuç, olarak gösterilemeyecek kadar büyükse **`long`** , sonuç tanımsızdır.|
|**`float`**|**`long long`**|Ondalık noktada kesin. Sonuç, olarak gösterilemeyecek kadar büyükse **`long long`** , sonuç tanımsızdır.|
|**`float`**|**`unsigned char`**|Dönüştür **`long`** ; Dönüştür **`long`****`unsigned char`**|
|**`float`**|**`unsigned short`**|Dönüştür **`long`** ; Dönüştür **`long`****`unsigned short`**|
|**`float`**|**`unsigned`**|Ondalık noktada kesin. Sonuç, olarak gösterilemeyecek kadar büyükse **`unsigned`** , sonuç tanımsızdır.|
|**`float`**|**`unsigned long`**|Ondalık noktada kesin. Sonuç, olarak gösterilemeyecek kadar büyükse **`unsigned long`** , sonuç tanımsızdır.|
|**`float`**|**`unsigned long long`**|Ondalık noktada kesin. Sonuç, olarak gösterilemeyecek kadar büyükse **`unsigned long long`** , sonuç tanımsızdır.|
|**`float`**|**`double`**|Olarak temsil eder **`double`** .|
|**`float`**|**`long double`**|Olarak temsil eder **`long double`** .|
|**`double`**|**`char`**|Dönüştür **`float`** ; Dönüştür **`float`****`char`**|
|**`double`**|**`short`**|Dönüştür **`float`** ; Dönüştür **`float`****`short`**|
|**`double`**|**`int`**|Ondalık noktada kesin. Sonuç, olarak gösterilemeyecek kadar büyükse **`int`** , sonuç tanımsızdır.|
|**`double`**|**`long`**|Ondalık noktada kesin. Sonuç, olarak gösterilemeyecek kadar büyükse **`long`** , sonuç tanımsızdır.|
|**`double`**|**`unsigned char`**|Dönüştür **`long`** ; Dönüştür **`long`****`unsigned char`**|
|**`double`**|**`unsigned short`**|Dönüştür **`long`** ; Dönüştür **`long`****`unsigned short`**|
|**`double`**|**`unsigned`**|Ondalık noktada kesin. Sonuç, olarak gösterilemeyecek kadar büyükse **`unsigned`** , sonuç tanımsızdır.|
|**`double`**|**`unsigned long`**|Ondalık noktada kesin. Sonuç, olarak gösterilemeyecek kadar büyükse **`unsigned long`** , sonuç tanımsızdır.|
|**`double`**|**`unsigned long long`**|Ondalık noktada kesin. Sonuç, olarak gösterilemeyecek kadar büyükse **`unsigned long long`** , sonuç tanımsızdır.|
|**`double`**|**`float`**|Olarak temsil eder **`float`** . **`double`** Değer tam olarak olarak temsil edileyemediğinde **`float`** duyarlık kaybı oluşur. Değer olarak gösterilemeyecek kadar büyükse **`float`** , sonuç tanımsızdır.|
|**`double`**|**`long double`**|**`long double`** Değer olarak değerlendirilir **`double`** .|

Dönüşümlerden dönüşümler, ' den **`long double`** dönüştürmelerde aynı yöntemi izler **`double`** .

## <a name="see-also"></a>Ayrıca bkz.

[Atama dönüştürmeleri](../c-language/assignment-conversions.md)

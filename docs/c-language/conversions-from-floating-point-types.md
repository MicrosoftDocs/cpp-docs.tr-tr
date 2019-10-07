---
title: Kayan nokta türlerinden dönüşümler
ms.date: 10/02/2019
helpviewer_keywords:
- converting floating point
- floating-point conversion
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
ms.openlocfilehash: c2f7c25015b36545f969796a1f85d355d715427a
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998702"
---
# <a name="conversions-from-floating-point-types"></a>Kayan nokta türlerinden dönüşümler

Diğer kayan nokta türüne dönüştürülen bir kayan nokta değeri, orijinal değerin sonuç türünde tam olarak gösterilebilir olması durumunda değer üzerinde değişiklik yapılmaz. Özgün değer sayısal ise, ancak tam olarak gösterilemeyen, sonuç bir sonraki daha büyük veya daha düşük bir sonraki değer olan değerdir. Kayan nokta türleri aralığı için [kayan nokta sabitleri sınırlarına](../c-language/limits-on-floating-point-constants.md) bakın.

Tamsayı türüne dönüştürülen bir kayan nokta değeri ilk olarak kesirli değer atılarak kesilir. Bu kesilen değer sonuç türünde gösterilebilir ise, sonuç bu değer olmalıdır. Gösterilemeyen bir tablo olmadığında sonuç değeri tanımsızdır.

**Microsoft 'a özgü**

Microsoft derleyicileri, **kayan** değerler için ıeee-754 binary32 temsili ve **uzun çift** ve **çift**için binary64 gösterimi kullanır. **Long Double** ve **Double** aynı gösterimi kullandığından, aynı aralığa ve duyarlığa sahiptir.

Derleyici bir **Double** veya **Long Double** kayan nokta numarasını bir **float**öğesine dönüştürdüğünde, varsayılan olarak "en yakına yuvarlanır" olarak "en yakın" ' a yuvarlayacak şekilde kayan nokta ortam denetimlerine göre sonucu yuvarlar. Sayısal bir değer çok yüksek veya sayısal bir **float** değeri olarak gösterilemeyecek kadar düşükse, dönüştürme sonucu özgün değerin işaretine göre pozitif veya negatif sonsuzluk olur ve etkinleştirilirse bir taşma özel durumu oluşturulur.

Tamsayı türlerine dönüştürme yaparken, değerden küçük bir türe dönüştürmenin sonucu değerin **Long**değerine dönüştürülmesi ve sonra sonuç türüne dönüştürülmesi **sonucu olur.**

Tamsayı türlerine en az **Long**kadar büyük olan dönüştürme için, sonuç türünde temsil etmek için çok yüksek veya çok düşük bir değer dönüştürmesi aşağıdaki değerlerden herhangi birini döndürebilir:

- Sonuç, sıfırdan en uzak gösterilemeyen bir değer olan *Sentinel değeri*olabilir. İmzalı türler için en düşük gösterilebilir tablo değeridir (0x800... 0). İmzasız türler için en yüksek gösterilebilir tablo değeridir (0xFF... F).

- Sonuç, değerlerin temsil edildiği çok yüksek değeri en yüksek gösterilemeyen değere dönüştürüldüğü ve temsil etmek için çok düşük değerler en düşük gösterilemeyen değere dönüştürülerek *doygun*olabilir. Bu iki değerden biri Sentinel değeri olarak da kullanılır.

- **İşaretsiz Long** veya **işaretsiz Long**Long 'a dönüştürme için, Aralık dışı bir değeri dönüştürmenin sonucu, en yüksek veya en düşük gösterilemeyen değer dışında bir değer olabilir. Sonucun Sentinel veya doygun bir değer olup olmadığı veya derleyicinin seçeneklerine ve hedef mimarisine bağlı olup olmadığı. Gelecekteki derleyici yayınları, bunun yerine bir doygun veya Sentinel değeri döndürebilir.

**SON Microsoft 'a özgü**

Aşağıdaki tabloda, kayan türlerden dönüşümler özetlenmektedir.

## <a name="table-of-conversions-from-floating-point-types"></a>Kayan nokta türlerinden dönüştürme tablosu

|Başlangıç|Bitiş|Yöntem|
|----------|--------|------------|
|**float**|**char**|**Long**'a Dönüştür; **Long** **karakter** olarak Dönüştür|
|**float**|**short**|**Long**'a Dönüştür; **Long** 'ı **Short** 'a Dönüştür|
|**float**|**int**|Ondalık noktada kesin. Sonuç **int**olarak gösterilemeyecek kadar büyükse, sonuç tanımsızdır.|
|**float**|**long**|Ondalık noktada kesin. Sonuç **uzun**olarak gösterilemeyecek kadar büyükse, sonuç tanımsızdır.|
|**float**|**uzun uzun**|Ondalık noktada kesin. Sonuç **uzun**bir süre gösterilemeyecek kadar büyükse, sonuç tanımsızdır.|
|**float**|**işaretsiz karakter**|**Long**'a Dönüştür; **Long** **karakteri işaretsiz karakter** olarak Dönüştür|
|**float**|**işaretsiz kısa**|**Long**'a Dönüştür; **uzun** **işaretsiz kısa** Dönüştür|
|**float**|**işaretlenmemiş**|Ondalık noktada kesin. Sonuç **işaretsiz**olarak gösterilemeyecek kadar büyükse, sonuç tanımsızdır.|
|**float**|**imzasız Long**|Ondalık noktada kesin. Sonuç **işaretsiz Long**olarak gösterilemeyecek kadar büyükse, sonuç tanımsızdır.|
|**float**|**imzasız uzun uzun**|Ondalık noktada kesin. Sonuç, **imzasız uzun Long**olarak gösterilemeyecek kadar büyükse, sonuç tanımsızdır.|
|**float**|**double**|**Double**olarak temsil eder.|
|**float**|**uzun çift**|**Uzun çift**olarak temsil eder.|
|**double**|**char**|**Float**öğesine Dönüştür; **float** öğesini **char** 'a Dönüştür|
|**double**|**short**|**Float**öğesine Dönüştür; **float** öğesini **Short** 'a Dönüştür|
|**double**|**int**|Ondalık noktada kesin. Sonuç **int**olarak gösterilemeyecek kadar büyükse, sonuç tanımsızdır.|
|**double**|**long**|Ondalık noktada kesin. Sonuç **uzun**olarak gösterilemeyecek kadar büyükse, sonuç tanımsızdır.|
|**double**|**işaretsiz karakter**|**Long**'a Dönüştür; **Long** **karakteri işaretsiz karakter** olarak Dönüştür|
|**double**|**işaretsiz kısa**|**Long**'a Dönüştür; **uzun** **işaretsiz kısa** Dönüştür|
|**double**|**işaretlenmemiş**|Ondalık noktada kesin. Sonuç **işaretsiz**olarak gösterilemeyecek kadar büyükse, sonuç tanımsızdır.|
|**double**|**imzasız Long**|Ondalık noktada kesin. Sonuç **işaretsiz Long**olarak gösterilemeyecek kadar büyükse, sonuç tanımsızdır.|
|**double**|**imzasız uzun uzun**|Ondalık noktada kesin. Sonuç, **imzasız uzun Long**olarak gösterilemeyecek kadar büyükse, sonuç tanımsızdır.|
|**double**|**float**|**Float**olarak temsil eder. **Double** değeri tam olarak **float**olarak temsil edileyemediğinde duyarlık kaybı oluşur. Değer **float**olarak gösterilemeyecek kadar büyükse, sonuç tanımsızdır.|
|**double**|**uzun çift**|**Long Double** değeri **Double**olarak değerlendirilir.|

**Uzun çift** dönüşümlerden dönüştürmeler, **Double**'tan dönüştürmelerde aynı yöntemi izler.

## <a name="see-also"></a>Ayrıca bkz.

[Atama dönüştürmeleri](../c-language/assignment-conversions.md)

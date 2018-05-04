---
title: Tür float | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- type float
- exponent length
- float keyword [C]
- mantissas, length
- floating-point numbers, float type
- ranges, floating-point types
- floating-point numbers, variables
- lengths, mantissa
- double data type, type float
- IEEE floating-point representation
- lengths, exponent
ms.assetid: 706e332b-17a0-4a30-b7d8-5d6cd372524b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e218f7b5025de10dc06bf20fc759aed93189ec53
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="type-float"></a>Tür float
Kayan nokta sayıları IEEE (Institute of Electrical and Electronics Engineers) biçimini kullanın. Tek duyarlıklı kayan noktalı sayı türü değerlerle oturum bit, 8 bit aşırı 127 ikili üs ve 23 bit Mantis oluşan 4 bayt vardır. Mantis 1.0 ve 2.0 arasında bir sayı temsil eder. Mantis yüksek sıra biti 1 her zaman olduğundan sayısında depolanmaz. Bu gösterim yaklaşık 3.4E bir dizi sağlar-3.4E + 38 tür float için 38.  
  
 Float olarak ya da, uygulamanızın gereksinimlerine bağlı olarak, çift değişkenleri bildirebilirsiniz. İki tür arasındaki asıl farklılıklar temsil edebilir anlamlı, gereksinim duydukları depolama ve menzil ' dir. Aşağıdaki tabloda önem ve depolama gereksinimleri arasındaki ilişkiyi gösterir.  
  
### <a name="floating-point-types"></a>Kayan nokta türleri  
  
|Tür|Önemli basamak|Bayt sayısı|  
|----------|------------------------|---------------------|  
|float|6 - 7|4|  
|çift|15 - 16|8|  
  
 Kayan nokta değişkenleri sayısı ve büyüklük numarasını içeren bir üs değerini içeren bir Mantis temsil edilir.  
  
 Aşağıdaki tabloda Mantis ve üs her kayan nokta türü için ayrılmış bit sayısını gösterir. Bir kayan noktalı sayı veya çift en önemli bit her zaman işaret bitidir. 1. sayı negatif kabul edilir; Aksi takdirde, pozitif bir sayı olarak kabul edilir.  
  
### <a name="lengths-of-exponents-and-mantissas"></a>Üsler ve Mantisler uzunlukları  
  
|Tür|Üs uzunluğu|Mantis uzunluğu|  
|----------|---------------------|---------------------|  
|float|8 bit|23 BITS|  
|çift|11 bit|52 BITS|  
  
 Üs imzasız formunda depolandığından, üs yarım olası değer tarafından ağırlıklı. Tür float için sapması 127'dir; double türü için onu 1023 ' dir. Eğilim değeri üs değerinden çıkararak gerçek üs değeri hesaplayabilirsiniz.  
  
 Mantis ikili bir kesir değerinden büyük veya 1 ve 2'den eşit olarak depolanır. Türleri float ve double için olmadığından zımni başında 1 Mantis en önemli bit konumda en önemli bit hiçbir zaman bellekte depolanır olsa bile mantisler gerçekten 24 ve 53 uzun, sırasıyla bittir.  
  
 Yalnızca açıklanan depolama yöntemi yerine kayan nokta paket ikili kayan nokta sayıları Normalleştirilmemiş sayı olarak depolayabilirsiniz. "Normalleştirilmemiş" sıfır olmayan bir kayan nokta sayıları Mantis en önemli biti 0 olduğu ayrılmış üs değerlerle numaralarıdır. Normalleştirilmemiş biçimi kullanarak bir kayan noktalı sayı aralığı, duyarlık genişletilebilir. Bir kayan noktalı sayının normalleştirilmiş veya Normalleştirilmemiş formunda temsil edilen denetleyemez; kayan nokta paket gösterimi belirler. Kayan nokta paket üs hale sürece hiçbir zaman Normalleştirilmemiş bir form kullanır. normalleştirilmiş bir formda temsil edilebilir en küçük değerinden.  
  
 Aşağıdaki tabloda, her bir kayan nokta türü değişkenlerde depolayabilir minimum ve maksimum değerleri gösterir. Bu tabloda listelenen değerleri yalnızca normalleştirilmiş kayan nokta sayıları için geçerlidir; Normalleştirilmemiş kayan nokta sayıları daha küçük bir en düşük değere sahip. 80 korunur sayıların Not*x*87 kayıtları her zaman 80 bit normalleştirilmiş biçiminde temsil; numaraları yalnızca temsil 32 bit veya 64-bit kayan nokta değişkenleri (tür float değişkenlerinin depolandığında Normalleştirilmemiş formunda ve uzun yazın).  
  
### <a name="range-of-floating-point-types"></a>Kayan nokta türleri aralığı  
  
|Tür|Minimum değer|En büyük değer|  
|----------|-------------------|-------------------|  
|float|1.175494351 E - 38|3.402823466 E + 38|  
|çift|2.2250738585072014 E - 308|1.7976931348623158 E + 308|  
  
 Duyarlık sorun depolama daha küçükse, kayan nokta değişkenleri tür float kullanmayı düşünün. Buna karşılık, duyarlık en önemli bir ölçüt ise, türü çift kullanın.  
  
 Kayan nokta değişkenleri (tür double için tür float) büyük anlamlı türüne yükseltilebilir. Kayan nokta değişkenleri aritmetik gerçekleştirdiğinizde genellikle yükseltme oluşur. Bu aritmetik her zaman yüksek duyarlık derecesini Duyarlık yüksek derecede değişkenle olarak yapılır. Örneğin, aşağıdaki türde bildirimlerden göz önünde bulundurun:  
  
```  
float f_short;  
double f_long;  
long double f_longer;  
  
f_short = f_short * f_long;  
```  
  
 Önceki örnekte, değişken `f_short` tür double görmeleri ve ile çarpılır `f_long`; sonucu önce atanmasına tür float yuvarlanır sonra `f_short`.  
  
 Aritmetik float (32 bit) duyarlık değişkenleri yapılır (hangi bildirimleri önceki örnekten kullanır) aşağıdaki örnekte, Sonuç, ardından tür double için yükseltilir:  
  
```  
f_longer = f_short * f_short;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel Türleri Depolama](../c-language/storage-of-basic-types.md)
---
title: L-değeri ve r değeri ifadeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- L-values
- member-selection expressions
- R-value expressions
- subscript expressions
ms.assetid: b790303e-ec6f-4d0d-bc55-df42da267172
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 654805750b3cd17e2157fa3710791493970b371f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="l-value-and-r-value-expressions"></a>L-Değeri ve R-Değeri İfadeleri
Bellek konumları ifadeleri "l-değeri" ifadeleri denir. L-değeri eşittir işaretinden sol tarafta görünebilir olduğunu belirtmek "sol" bir değer veya bir depolama bölgenin "Bulucusu" değerini temsil eder (**=**). L değerleri genellikle tanımlayıcılardır.  
  
 Değiştirilebilir konumlara başvuran ifadeleri "değiştirilebilir l değerleri." olarak adlandırılır Bir dizi türü, tamamlanmamış bir tür ya da bir türü ile değiştirilebilir l-değeri olamaz **const** özniteliği. Yapılar ve birleşimler değiştirilebilir l değerleri olması için bunlar herhangi üyeleriyle olmamalıdır **const** özniteliği. O konumda saklanan değeri olsa da değişkenin değeri olarak bir depolama konumu tanımlayıcı adını gösterir.  
  
 Bir değiştirilebilir l-değeri bir bellek konumuna başvurduğu olmadığını ve aritmetik, yapısı, UNION veya işaretçi türü olup olmadığını tanımlayıcısıdır. Örneğin, varsa `ptr` bir işaretçi bir depolama bölgesi ise `*ptr` bir değiştirilebilir l-, depolama bölgesine atayan değer `ptr` noktaları.  
  
 L-değeri ifadeleri aşağıdaki C ifadelerden herhangi biri olabilir:  
  
-   İntegral, kayan, işaretçi, yapı veya birleşim türü bir tanımlayıcı  
  
-   Bir alt simge (**[]**) için bir dizi değerlendirmez ifade  
  
-   Üye seçim ifade (**->** veya **.**)  
  
-   Birli yöneltme (**\***) için bir dizi başvurmuyor ifade  
  
-   L-değeri ifadesi parantez içinde  
  
-   A **const** nesne (değiştirilemez l-değeri)  
  
 "R" terimi, bazen bir ifadenin değerini açıklamak için ve bir m değerinden ayırt etmek için kullanılır. Tüm l-r değerleri değerlerdir ancak tüm r-l değerleri değerlerdir.  
  
 **Microsoft özel**  
  
 Microsoft C nesnenin boyutu cast uzatılmış değil sürece değerlerin l-m-değerler olarak kullanılacak atamaları sağlayan ANSI C standardı uzantısı içerir. (Bkz [tür atama dönüşümleri](../c-language/type-cast-conversions.md) daha fazla bilgi için.) Aşağıdaki örnekte, bu özelliği gösterilmektedir:  
  
```  
char *p ;  
short  i;  
long l;  
  
(long *) p = &l ;       /* Legal cast   */  
(long) i = l ;          /* Illegal cast */  
```  
  
 Microsoft C için Microsoft uzantıları etkinleştirildiğini varsayılandır. Bu uzantıları devre dışı bırakmak için /Za derleyici seçeneği kullanın.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlenenler ve İfadeler](../c-language/operands-and-expressions.md)
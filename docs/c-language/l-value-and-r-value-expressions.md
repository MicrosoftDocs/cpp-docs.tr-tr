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
ms.openlocfilehash: 133a88494cfb318b39c5b16191ee8463037f1fac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055311"
---
# <a name="l-value-and-r-value-expressions"></a>L-Değeri ve R-Değeri İfadeleri

Bellek konumlarına başvurmak ifadeleri "l-value" ifadeleri çağrılır. Bir l değeri eşittir işaretinin sol tarafında görünebilir olduğunu belirtmek, "sol" bir değer veya bir depolama bölgenin "Konum Belirleyicisi" değerini temsil eder (**=**). L-değerler genellikle tanıtıcılardır.

İfadeleri değiştirilebilir konumlara başvuran "değiştirilebilir ı-değerleri." olarak adlandırılır Bir dizi türü, tamamlanmamış bir türü veya bir tür ile değiştirilebilir bir l-değeri olamaz **const** özniteliği. Yapılar ve birleşimler değiştirilebilir bir l-değeri olması için bunların herhangi bir üye olmamalıdır **const** özniteliği. O konumda depolanan değeri olsa da değişkenin değeri olarak bir depolama konumu tanımlayıcı adını gösterir.

Bir tanımlayıcı, bir bellek konumuna başvuruyorsa ve aritmetik, yapı, birleşim veya işaretçi türü ise, değiştirilebilir bir l-değeri olan. Örneğin, varsa `ptr` bir depolama bölgesi için bir işaretçi ise `*ptr` değiştirilebilir bir l-depolama bölgesine belirten değeri olan `ptr` noktaları.

Aşağıdaki C deyimleri l-değeri ifadeleri olabilir:

- Bir tamsayı, kayan, işaretçi, yapı veya birleşim türü tanımlayıcısı

- Bir alt simge (**[]**) için bir dizi değerlendirmez ifadesi

- Üye seçimi ifade (**->** veya **.**)

- Birli yöneltme (<strong>\*</strong>) için bir dizi başvurmuyor ifadesi

- Parantez içinde bir l-değeri ifadesi

- A **const** nesne (değiştirilemez l-değeri)

"R" terimi, bazen bir ifadenin değerini tanımlamak ve bir l-değerden ayırmak için kullanılır. Tüm l-değerler r değerlerdir ancak tüm r değerleri l-değerler.

**Microsoft'a özgü**

Microsoft C yayınları l-değerler kullanılacak l-değerler nesnenin boyutunu atama uzatılmış değil sürece veren ANSI C standardının bir uzantısı içerir. (Bkz [tür atama dönüştürmeleri](../c-language/type-cast-conversions.md) daha fazla bilgi için.) Bu özellik aşağıdaki örnekte gösterilmiştir:

```
char *p ;
short  i;
long l;

(long *) p = &l ;       /* Legal cast   */
(long) i = l ;          /* Illegal cast */
```

Microsoft C için varsayılan Microsoft genişletmelerinin etkinleştirilmiş olduğu. Bu uzantıları devre dışı bırakmak için /Za derleyici seçeneğini kullanın.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[İşlenenler ve İfadeler](../c-language/operands-and-expressions.md)
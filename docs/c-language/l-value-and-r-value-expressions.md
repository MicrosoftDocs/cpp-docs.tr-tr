---
title: L-Değeri ve R-Değeri İfadeleri
ms.date: 11/04/2016
helpviewer_keywords:
- L-values
- member-selection expressions
- R-value expressions
- subscript expressions
ms.assetid: b790303e-ec6f-4d0d-bc55-df42da267172
ms.openlocfilehash: 0c287c45f2d7ea121c9c706b3b761ff7ce6ec232
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87199834"
---
# <a name="l-value-and-r-value-expressions"></a>L-Değeri ve R-Değeri İfadeleri

Bellek konumlarına başvuran ifadeler "l-value" ifadeleri olarak adlandırılır. Bir l-değeri, bir depolama bölgesinin "Konumlandırıcı" değerini veya "left" değerini temsil eder. Bu, eşittir işaretinin solunda () görünebilirler **=** . L-Values genellikle tanımlayıcılardır.

Değiştirilebilir konumlara başvuran ifadelere "değiştirilebilir l-Values" adı verilir. Değiştirilebilir bir l-değeri bir dizi türü, tamamlanmamış bir tür veya özniteliğe sahip bir tür olamaz **`const`** . Yapılar ve birleşimler için, değiştirilebilir l-Values olması için, özniteliğe sahip hiçbir üye içermemelidir **`const`** . Tanımlayıcının adı bir depolama konumunu belirtir, ancak değişkenin değeri o konumda depolanan değerdir.

Bir tanımlayıcı, bir bellek konumuna başvuruyorsa ve türü aritmetik, yapı, birleşim veya işaretçi ise değiştirilebilir bir l değeridir. Örneğin, bir `ptr` depolama bölgesinin işaretçisiyse, `*ptr` Depolama bölgesini işaret eden noktaya atayan değiştirilebilir bir l değeri `ptr` .

Aşağıdaki C ifadelerinin herhangi biri l-Value ifadesi olabilir:

- İntegral, kayan, işaretçi, yapı veya birleşim türü tanımlayıcısı

- Bir dizi olarak değerlendirilmeyecek bir alt simge (**[]**) ifadesi

- Üye seçim ifadesi ( **->** veya **.**)

- <strong>\*</strong>Bir diziye başvurmayan birli-yöneltme () ifadesi

- Parantez içinde bir l-değer ifadesi

- Bir **`const`** nesne (değiştirilemeyen bir l değeri)

"R-value" terimi bazen bir ifadenin değerini tanımlamak ve onu bir l değerinden ayırmak için kullanılır. Tüm l değerleri r-Values, ancak tüm r değerleri l-Values değildir.

**Microsoft'a Özgü**

Microsoft C, ANSI C standardına, nesne boyutunun dönüştürme yoluyla UZAMAYAN sürece l-Values olarak kullanılmasına izin veren bir uzantısı içerir. (Daha fazla bilgi için bkz. [tür dönüştürme dönüştürmeleri](../c-language/type-cast-conversions.md) .) Aşağıdaki örnek bu özelliği göstermektedir:

```
char *p ;
short  i;
long l;

(long *) p = &l ;       /* Legal cast   */
(long) i = l ;          /* Illegal cast */
```

Microsoft C için varsayılan değer, Microsoft uzantılarının etkinleştirilme içindir. Bu uzantıları devre dışı bırakmak için/Za derleyici seçeneğini kullanın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[İşlenenler ve Ifadeler](../c-language/operands-and-expressions.md)

---
title: L-Değeri ve R-Değeri İfadeleri
ms.date: 11/04/2016
helpviewer_keywords:
- L-values
- member-selection expressions
- R-value expressions
- subscript expressions
ms.assetid: b790303e-ec6f-4d0d-bc55-df42da267172
ms.openlocfilehash: bd5f702588a11b7841f77de539d113206833cde9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325526"
---
# <a name="l-value-and-r-value-expressions"></a>L-Değeri ve R-Değeri İfadeleri

Bellek konumlarına başvuran ifadeler "l-value" ifadeleri olarak adlandırılır. Bir l-değeri, bir depolama bölgesinin "Konumlandırıcı" değerini veya "left" değerini temsil eder. Bu, eşittir işaretinin solunda (**=**) görünebilirler. L-Values genellikle tanımlayıcılardır.

Değiştirilebilir konumlara başvuran ifadelere "değiştirilebilir l-Values" adı verilir. Değiştirilebilir bir l-değeri bir dizi türü, tamamlanmamış bir tür ya da **const** özniteliği olan bir tür olamaz. Yapılar ve birleşimler için, **sabit** özniteliğine sahip hiçbir üye içermemelidir. Tanımlayıcının adı bir depolama konumunu belirtir, ancak değişkenin değeri o konumda depolanan değerdir.

Bir tanımlayıcı, bir bellek konumuna başvuruyorsa ve türü aritmetik, yapı, birleşim veya işaretçi ise değiştirilebilir bir l değeridir. Örneğin, `ptr` bir depolama bölgesinin işaretçisiyse, `*ptr` depolama bölgesini `ptr` işaret eden noktaya atayan değiştirilebilir bir l değeri.

Aşağıdaki C ifadelerinin herhangi biri l-Value ifadesi olabilir:

- İntegral, kayan, işaretçi, yapı veya birleşim türü tanımlayıcısı

- Bir dizi olarak değerlendirilmeyecek bir alt simge (**[]**) ifadesi

- Üye seçim ifadesi (**->** veya **.**)

- Bir diziye başvurmayan birli<strong>\*</strong>-yöneltme () ifadesi

- Parantez içinde bir l-değer ifadesi

- Bir **const** nesnesi (değiştirilemeyen bir l değeri)

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

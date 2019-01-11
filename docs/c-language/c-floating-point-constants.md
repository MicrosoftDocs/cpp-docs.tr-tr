---
title: C Kayan Nokta Sabitleri
ms.date: 11/04/2016
helpviewer_keywords:
- types [C], constants
- floating-point numbers, floating-point constants
- constants, floating-point
- floating-point constants
- floating-point constants, about floating-point constants
- double data type, floating-point constants
ms.assetid: e1bd9b44-d6ab-470c-93e5-07142c7a2062
ms.openlocfilehash: 2bde8ecdfa7e93160a86829c466ab9a78b71d48e
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220380"
---
# <a name="c-floating-point-constants"></a>C Kayan Nokta Sabitleri

"Kayan noktalı sabit" temsil eden imzalı bir gerçek sayı bir ondalık sayıdır. Bir tamsayı kısmı, kesirli bölümü ve bir üs imzalı bir gerçek sayı gösterimini içerir. Kayan nokta sabitleri değiştirilemez kayan nokta değerlerini temsil edecek şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

*Kayan noktaya sabiti*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Sabit kesirli* *üs bölümü*<sub>iyileştirilmiş</sub> *kayan soneki*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*basamak dizisi* *üs bölümü* *kayan soneki*<sub>iyileştirilmiş</sub>

*Sabit kesirli*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*basamak dizisi*<sub>iyileştirilmiş</sub> **.** *basamak dizisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*basamak dizisi***.**

*Üs bölümü*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**e** *oturum*<sub>iyileştirilmiş</sub> *basamak dizisi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**e** *oturum*<sub>iyileştirilmiş</sub> *basamak dizisi*

*oturum*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**+ -**

*basamak dizisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*basamak*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*basamak dizisi* *basamak*

*Kayan soneki*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**f m F M**

Rakamları ondalık (değer tamsayı kısmını) önce veya basamak (kesirli kısmı) ondalık ayırıcıdan sonra ancak ikisi atlayabilirsiniz. Bir üssü içeriyorsa ondalık bırakabilirsiniz. Hiçbir boşluk karakterleri rakam veya karakter sabitinin ayırabilirsiniz.

Aşağıdaki örnekler, kayan nokta sabitleri ve ifadeler bazı forms gösterir:

```C
15.75
1.575E1   /* = 15.75   */
1575e-2   /* = 15.75   */
-2.5e-3   /* = -0.0025 */
25E-4     /* =  0.0025 */
```

Bunlar bir eksi işareti tarafından öncelenen sürece kayan nokta sabitleri pozitif (**-**). Bu durumda, eksi işareti birli aritmetik olumsuzlama işleci olarak kabul edilir. Kayan nokta sabitleri `float`, `double`, veya `long double`.

Bir kayan noktalı sabit olmayan bir **f**, **F**, **l**, veya **L** soneki türüne sahip `double`. Varsa harfi **f** veya **F** soneki sabiti türüne sahip olan `float`. Harfinin olup olmadığını **l** veya **L**, türüne sahip `long double`. Örneğin:

```C
10.0L  /* Has type long double  */
10.0F  /* Has type float        */
```

Microsoft C derleyicisi dahili olarak temsil eden Not `long double` türle aynı `double`. Bkz: [temel türlerin depolanması](../c-language/storage-of-basic-types.md) türü hakkında bilgi için `double`, `float`, ve `long double`.

Aşağıdaki örneklerde gösterildiği gibi kayan noktalı sabit tamsayı kısmını atlayabilirsiniz. Aşağıdakiler dahil olmak üzere birçok şekilde.75 sayısı belirtilebilir:

```C
.0075e2
0.075e1
.075e1
75e-2
```

## <a name="see-also"></a>Ayrıca Bkz.

[C Sabitleri](../c-language/c-constants.md)

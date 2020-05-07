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
ms.openlocfilehash: 5e17490926ee328c3a4ca03b1de9cb6e752959a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325687"
---
# <a name="c-floating-point-constants"></a>C Kayan Nokta Sabitleri

"Kayan nokta sabiti", işaretli bir gerçek sayıyı temsil eden ondalık bir sayıdır. İşaretli gerçek bir sayının temsili bir tamsayı bölümü, kesirli bölüm ve üs içerir. Değiştirilemeyen kayan nokta değerlerini göstermek için kayan nokta sabitleri kullanın.

## <a name="syntax"></a>Sözdizimi

*kayan nokta-sabit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*kesirli sabit* *üs-bölüm*<sub>opt</sub> *kayan-sonek*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*basamak sırası* *üs-bölüm* *kayan-sonek*<sub>opt</sub>

*kesirli sabit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*basamak sırası*<sub>katılımı</sub> **.** *basamak sırası*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*basamak sırası*  **.**

*üs-bölüm*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**e** *imza*<sub>opt</sub> *basamak sırası*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**E** *imza*<sub>opt</sub> *basamak sırası*

*imzala*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**+ -**

*basamak sırası*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Gurmukhi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*basamak sırası* *sayısı*

*kayan sonek*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**f l F L**

Ondalık noktadan önceki rakamları (değerin tamsayı kısmı) veya ondalık ayırıcıdan sonraki rakamları (kesirli bölüm) atlayabilirsiniz, ancak ikisini birden kullanamazsınız. Ondalık noktasını yalnızca bir üs dahil etmeniz durumunda bırakabilirsiniz. Boşluk karakterleri, sabitin rakamlarını veya karakterlerini ayırabilirler.

Aşağıdaki örneklerde bazı kayan nokta sabitleri ve ifadeleri gösterilmektedir:

```C
15.75
1.575E1   /* = 15.75   */
1575e-2   /* = 15.75   */
-2.5e-3   /* = -0.0025 */
25E-4     /* =  0.0025 */
```

Kayan nokta sabitleri önünde eksi işareti (**-**) belirtilmedikçe pozitif. Bu durumda, eksi işareti birli aritmetik olumsuzlama işleci olarak değerlendirilir. Kayan nokta sabitleri, `float` `double`veya `long double`türündedir.

**F**, **f**, **l**veya **l** soneki olmayan bir kayan nokta sabiti türü `double`vardır. **F** veya **f** harfi sonek ise, sabit tür `float`olur. **L** veya **l**harfi tarafından düzeltildiğinde, türü `long double`vardır. Örneğin:

```C
10.0L  /* Has type long double  */
10.0F  /* Has type float        */
```

Microsoft C derleyicisi 'nin, türü `long double` `double`ile aynı şekilde temsil ettiğini unutmayın. , `float`Ve `long double`türü `double`hakkında bilgi için bkz. [temel türlerin depolanması](../c-language/storage-of-basic-types.md) .

Aşağıdaki örneklerde gösterildiği gibi kayan nokta sabitinin tamsayı bölümünü atlayabilirsiniz. Number. 75, aşağıdakiler dahil olmak üzere birçok şekilde ifade edilebilir:

```C
.0075e2
0.075e1
.075e1
75e-2
```

## <a name="see-also"></a>Ayrıca bkz.

[C Sabitleri](../c-language/c-constants.md)

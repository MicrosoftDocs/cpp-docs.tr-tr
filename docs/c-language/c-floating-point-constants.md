---
description: 'Daha fazla bilgi edinin: C Floating-Point sabitleri'
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
ms.openlocfilehash: 0bad45db33cd40060c4d20312c5318d443efc60f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293566"
---
# <a name="c-floating-point-constants"></a>C Kayan Nokta Sabitleri

"Kayan nokta sabiti", işaretli bir gerçek sayıyı temsil eden ondalık bir sayıdır. İşaretli gerçek bir sayının temsili bir tamsayı bölümü, kesirli bölüm ve üs içerir. Değiştirilemeyen kayan nokta değerlerini göstermek için kayan nokta sabitleri kullanın.

## <a name="syntax"></a>Syntax

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

Kayan nokta sabitleri önünde eksi işareti () belirtilmedikçe pozitif **-** . Bu durumda, eksi işareti birli aritmetik olumsuzlama işleci olarak değerlendirilir. Kayan nokta sabitleri **`float`** , **`double`** veya türündedir **`long double`** .

**F**, **f**, **l** veya **l** soneki olmayan bir kayan nokta sabiti türü vardır **`double`** . **F** veya **f** harfi sonek ise, sabit tür olur **`float`** . **L** veya **l** harfi tarafından düzeltildiğinde, türü vardır **`long double`** . Örneğin:

```C
10.0L  /* Has type long double  */
10.0F  /* Has type float        */
```

Microsoft C derleyicisi 'nin **`long double`** , türü ile aynı şekilde temsil ettiğini unutmayın **`double`** . , Ve türü hakkında bilgi için bkz. [temel türlerin depolanması](../c-language/storage-of-basic-types.md) **`double`** **`float`** **`long double`** .

Aşağıdaki örneklerde gösterildiği gibi kayan nokta sabitinin tamsayı bölümünü atlayabilirsiniz. Number. 75, aşağıdakiler dahil olmak üzere birçok şekilde ifade edilebilir:

```C
.0075e2
0.075e1
.075e1
75e-2
```

## <a name="see-also"></a>Ayrıca bkz.

[C sabitleri](../c-language/c-constants.md)

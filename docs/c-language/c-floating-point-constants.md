---
title: C kayan nokta sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- types [C], constants
- floating-point numbers, floating-point constants
- constants, floating-point
- floating-point constants
- floating-point constants, about floating-point constants
- double data type, floating-point constants
ms.assetid: e1bd9b44-d6ab-470c-93e5-07142c7a2062
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3608e40db2aa3eb0c49942de278c1d428e26689f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32385103"
---
# <a name="c-floating-point-constants"></a>C Kayan Nokta Sabitleri
"Kayan nokta sabiti" temsil eden imzalı bir gerçek sayı ondalık bir sayıdır. İmzalı bir gerçek sayı gösterimini bir tamsayı bölümü, bir kesirli kısmını ve üs içerir. Kayan nokta sabitleri değiştirilemez kayan nokta değerlerini temsil edecek şekilde kullanın.  
  
## <a name="syntax"></a>Sözdizimi  
 *Floating sabiti point*:  
 &nbsp;&nbsp; *sabiti kesirli üs parçalı*<sub>kabul</sub> *kayan soneki*<sub>iptal et</sub>  
 &nbsp;&nbsp; *Kayan basamak dizisi üs bölümü-soneki*<sub>iptal et</sub>  
  
 *sabiti kesirli*:  
 &nbsp;&nbsp; *basamak dizisi*<sub>kabul</sub> **.** *basamak dizisi*  
 &nbsp;&nbsp; *basamak dizisi***.**   
  
 *Üs bölümü*:  
 &nbsp;&nbsp; **e***oturum*<sub>kabul</sub> *basamak dizisi*   
 &nbsp;&nbsp; **E***oturum*<sub>kabul</sub> *basamak dizisi*   
  
 *oturum* : biri  
 &nbsp;&nbsp; **+ -**  
  
 *basamak dizisi*:  
 &nbsp;&nbsp; *Basamak*  
 &nbsp;&nbsp; *basamak dizisi basamak*  
  
 *Kayan soneki* : biri  
 &nbsp;&nbsp; **f l F M**  
  
 Rakamları (değeri tamsayı kısmını) ondalık ayırıcıdan önce veya basamak (kesirli kısmı) ondalık ayırıcıdan sonra ancak ikisi atlayabilirsiniz. Yalnızca bir üs eklerseniz, bir ondalık ayırıcısı bırakabilirsiniz. Hiçbir boşluk karakter, rakam veya karakter sabiti ayırabilirsiniz.  
  
 Aşağıdaki örneklerde, kayan nokta sabitleri ve ifadeler bazı formları gösterilmektedir:  
  
```  
15.75  
1.575E1   /* = 15.75   */  
1575e-2   /* = 15.75   */  
-2.5e-3   /* = -0.0025 */  
25E-4     /* =  0.0025 */  
```  
  
 Bir eksi işareti koyarak sürece kayan nokta sabitleri pozitif (**-**). Bu durumda, eksi işareti birli aritmetik değilleme işleci kabul edilir. Kayan nokta sabitleri türüne sahip `float`, `double`, veya `long double`.  
  
 Kayan nokta sabiti olmadan bir **f**, **F**, **l**, veya **L** soneki türüne sahip `double`. Varsa harf **f** veya **F** sahip sabit türü soneki eklenir `float`. Harfinin sonekine varsa **l** veya **L**, türüne sahip `long double`. Örneğin:  
  
```  
100L  /* Has type long double  */  
100F  /* Has type float        */  
```  
  
 Microsoft C Derleyici dahili olarak temsil eden Not `long double` türle aynı `double`. Bkz: [temel türleri depolama](../c-language/storage-of-basic-types.md) türü hakkında bilgi için `double`, `float`, ve `long double`.  
  
 Aşağıdaki örneklerde gösterildiği gibi kayan nokta sabiti tamsayı bölümünü atlayabilirsiniz. .75 numarası aşağıdakiler de dahil olmak üzere birçok yolla ifade edilebilir:  
  
```  
.0075e2  
0.075e1  
.075e1  
75e-2  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Sabitleri](../c-language/c-constants.md)
---
description: Sequential-Evaluation Işleci hakkında daha fazla bilgi edinin
title: Sıralı Değerlendirme İşleci
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], sequential-evaluation
- sequential-evaluation operator
- comma operator
ms.assetid: 587514f4-c8e2-44e9-81a8-7a553ce1453a
ms.openlocfilehash: 7bbe9bd6f70f32bd51e46df28f6e072edf9b6c15
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292799"
---
# <a name="sequential-evaluation-operator"></a>Sıralı Değerlendirme İşleci

"Virgül işleci" olarak da bilinen sıralı değerlendirme işleci, iki işlenenini soldan sağa sırayla değerlendirir.

## <a name="syntax"></a>Syntax

*ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade* **,** *atama ifadesi*

Sıralı değerlendirme işlecinin sol işleneni bir ifade olarak değerlendirilir **`void`** . İşlemin sonucu, sağ işleneniyle aynı değere ve türe sahiptir. Her işlenen herhangi bir türde olabilir. Sıralı değerlendirme işleci, işlenenleri arasında tür dönüştürmeleri gerçekleştirmez ve bir l değeri vermez. İlk işlenenden sonra bir dizi noktası vardır. Bu, sol işlenenin değerlendirmesinden gelen tüm yan etkilerin, doğru işlenenin değerlendirmesine başlamadan önce tamamlandıkları anlamına gelir. Daha fazla bilgi için bkz. [dizi noktaları](../c-language/c-sequence-points.md) .

Sıralı değerlendirme operatörü genellikle yalnızca bir ifadeye izin verilen bağlamlarda iki veya daha fazla ifadeyi değerlendirmek için kullanılır.

Virgüller, bazı bağlamlarda ayırıcı olarak kullanılabilir. Bununla birlikte, virgül kullanımını işleç olarak kullanımı ile ayırıcı olarak karıştırmamaya dikkat etmeniz gerekir; iki kullanım tamamen farklıdır.

## <a name="example"></a>Örnek

Bu örnekte sıralı değerlendirme operatörü gösterilmektedir:

```
for ( i = j = 1; i + j < 20; i += i, j-- );
```

Bu örnekte, **`for`** deyimin üçüncü ifadesinin her işleneni bağımsız olarak değerlendirilir. Sol işlenen `i += i` önce değerlendirilir, sonra sağ işlenen `j--` değerlendirilir.

```
func_one( x, y + 2, z );
func_two( (x--, y + 2), z );
```

İşlev çağrısında, `func_one` virgülle ayrılmış üç bağımsız değişken geçirilir: `x` , `y + 2` , ve `z` . `func_two` işlev çağrısında, parantezler derleyiciyi, ilk virgülü sıralı değerlendirme işleci olarak yorumlamaya zorlar. Bu işlev çağrısı, `func_two` öğesine iki bağımsız değişken geçirir. İlk bağımsız değişken, `(x--, y + 2)` ifadesinin değerine ve türüne sahip olan `y + 2` sıralı değerlendirme işleminin sonucudur; ikinci bağımsız değişken ise `z`'dir.

## <a name="see-also"></a>Ayrıca bkz.

[Virgül Işleci:,](../cpp/comma-operator.md)

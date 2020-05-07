---
title: Sıralı Değerlendirme İşleci
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], sequential-evaluation
- sequential-evaluation operator
- comma operator
ms.assetid: 587514f4-c8e2-44e9-81a8-7a553ce1453a
ms.openlocfilehash: 2cbffc51fb7113ae442dbfcd1db01bbf27a67746
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158527"
---
# <a name="sequential-evaluation-operator"></a>Sıralı Değerlendirme İşleci

"Virgül işleci" olarak da bilinen sıralı değerlendirme işleci, iki işlenenini soldan sağa sırayla değerlendirir.

## <a name="syntax"></a>Sözdizimi

*ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade* **,** *atama ifadesi*

Sıralı değerlendirme işlecinin sol işleneni bir `void` ifade olarak değerlendirilir. İşlemin sonucu, sağ işleneniyle aynı değere ve türe sahiptir. Her işlenen herhangi bir türde olabilir. Sıralı değerlendirme işleci, işlenenleri arasında tür dönüştürmeleri gerçekleştirmez ve bir l değeri vermez. İlk işlenenden sonra bir dizi noktası vardır. Bu, sol işlenenin değerlendirmesinden gelen tüm yan etkilerin, doğru işlenenin değerlendirmesine başlamadan önce tamamlandıkları anlamına gelir. Daha fazla bilgi için bkz. [dizi noktaları](../c-language/c-sequence-points.md) .

Sıralı değerlendirme operatörü genellikle yalnızca bir ifadeye izin verilen bağlamlarda iki veya daha fazla ifadeyi değerlendirmek için kullanılır.

Virgüller, bazı bağlamlarda ayırıcı olarak kullanılabilir. Bununla birlikte, virgül kullanımını işleç olarak kullanımı ile ayırıcı olarak karıştırmamaya dikkat etmeniz gerekir; iki kullanım tamamen farklıdır.

## <a name="example"></a>Örnek

Bu örnekte sıralı değerlendirme operatörü gösterilmektedir:

```
for ( i = j = 1; i + j < 20; i += i, j-- );
```

Bu örnekte, **for** deyiminin üçüncü ifadesinin her işleneni bağımsız olarak değerlendirilir. Sol işlenen `i += i` önce değerlendirilir; ardından, doğru işlenen `j--`değerlendirilir.

```
func_one( x, y + 2, z );
func_two( (x--, y + 2), z );
```

İşlev çağrısında `func_one`, virgülle ayrılmış üç bağımsız değişken geçirilir: `x`, `y + 2`, ve. `z` `func_two` işlev çağrısında, parantezler derleyiciyi, ilk virgülü sıralı değerlendirme işleci olarak yorumlamaya zorlar. Bu işlev çağrısı, `func_two` öğesine iki bağımsız değişken geçirir. İlk bağımsız değişken, `(x--, y + 2)` ifadesinin değerine ve türüne sahip olan `y + 2` sıralı değerlendirme işleminin sonucudur; ikinci bağımsız değişken ise `z`'dir.

## <a name="see-also"></a>Ayrıca bkz.

[Virgül İşleci: ,](../cpp/comma-operator.md)

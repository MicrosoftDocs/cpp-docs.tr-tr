---
title: Sıralı Değerlendirme İşleci
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], sequential-evaluation
- sequential-evaluation operator
- comma operator
ms.assetid: 587514f4-c8e2-44e9-81a8-7a553ce1453a
ms.openlocfilehash: 2cbffc51fb7113ae442dbfcd1db01bbf27a67746
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56149134"
---
# <a name="sequential-evaluation-operator"></a>Sıralı Değerlendirme İşleci

"Virgül işleci," olarak da bilinir sıralı değerlendirme işleci, kendi iki işlenenden sırayla soldan sağa doğru değerlendirilir.

## <a name="syntax"></a>Sözdizimi

*ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*expression* **,** *assignment-expression*

Sıralı değerlendirme işlecinin sol işleneni olarak değerlendirilen bir `void` ifade. İşlemin sonucunu, sağ işlenen aynı değerine ve türüne sahiptir. Her işlenen, herhangi bir türde olabilir. Sıralı değerlendirme işleci işlenenleri arasındaki tür dönüştürmeleri gerçekleştirmez ve bir l değeri vermez. Sonra sağ işlenenin değerlendirme başlamadan önce tüm yan etkiler değerlendirmesine sol işlenenin tamamlandığı anlamına gelir ilk işlenen, bir dizi noktası yoktur. Bkz: [dizi noktaları](../c-language/c-sequence-points.md) daha fazla bilgi için.

Sıralı değerlendirme işleci genellikle iki veya daha fazla ifade bağlamlarda değerlendirmek için burada yalnızca bir ifadeye izin kullanılır.

Virgüller, bazı bağlamlarda ayırıcılar olarak kullanılabilir. Ancak, virgül kullanımını işleç kullanımı ayırıcı olarak karıştırmamaya dikkatli olmanız gerekir; iki kullanım birbirinden tamamen farklıdır.

## <a name="example"></a>Örnek

Bu örnekte, sıralı değerlendirme işleci gösterilmektedir:

```
for ( i = j = 1; i + j < 20; i += i, j-- );
```

Bu örnekte, her işleneni **için** üçüncü ifade deyiminin bağımsız olarak değerlendirilir. Sol işlenen `i += i` değerlendirilen ilk; sonra sağ işlenen `j--`, değerlendirilir.

```
func_one( x, y + 2, z );
func_two( (x--, y + 2), z );
```

İşlev çağrısında `func_one`, virgülle ayrılmış üç bağımsız değişken geçirilir: `x`, `y + 2`, ve `z`. 
  `func_two` işlev çağrısında, parantezler derleyiciyi, ilk virgülü sıralı değerlendirme işleci olarak yorumlamaya zorlar. Bu işlev çağrısı, `func_two` öğesine iki bağımsız değişken geçirir. İlk bağımsız değişken, `(x--, y + 2)` ifadesinin değerine ve türüne sahip olan `y + 2` sıralı değerlendirme işleminin sonucudur; ikinci bağımsız değişken ise `z`'dir.

## <a name="see-also"></a>Ayrıca bkz.

[Virgül İşleci: ,](../cpp/comma-operator.md)

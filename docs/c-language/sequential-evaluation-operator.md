---
title: Sıralı değerlendirme işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], sequential-evaluation
- sequential-evaluation operator
- comma operator
ms.assetid: 587514f4-c8e2-44e9-81a8-7a553ce1453a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a285cc87ec4182586663afcb3559101167ae7261
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095579"
---
# <a name="sequential-evaluation-operator"></a>Sıralı Değerlendirme İşleci

"Virgül işleci," olarak da bilinir sıralı değerlendirme işleci, kendi iki işlenenden sırayla soldan sağa doğru değerlendirilir.

## <a name="syntax"></a>Sözdizimi

*ifade*: *atama ifadesi*

*ifade***,***atama ifadesi* 

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

İşlev çağrısında `func_one`, virgülle ayrılmış üç bağımsız değişken geçirilir: `x`, `y + 2`, ve `z`. `func_two` işlev çağrısında, parantezler derleyiciyi, ilk virgülü sıralı değerlendirme işleci olarak yorumlamaya zorlar. Bu işlev çağrısı, `func_two` öğesine iki bağımsız değişken geçirir. İlk bağımsız değişken, `(x--, y + 2)` ifadesinin değerine ve türüne sahip olan `y + 2` sıralı değerlendirme işleminin sonucudur; ikinci bağımsız değişken ise `z`'dir.

## <a name="see-also"></a>Ayrıca Bkz.

[Virgül İşleci: ,](../cpp/comma-operator.md)
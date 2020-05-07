---
title: Tür Dönüştürmeleri (C)
ms.date: 11/04/2016
helpviewer_keywords:
- conversions, type
- type conversion
- converting types
- integral promotions
- type casts, when performed
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
ms.openlocfilehash: 281234b857a97acbb57ebbfca7b678a637d00764
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346294"
---
# <a name="type-conversions-c"></a>Tür Dönüştürmeleri (C)

Tür dönüştürmeleri, belirtilen işlece ve işlenenin veya işleçlerin türüne bağlıdır. Tür dönüştürmeleri aşağıdaki durumlarda gerçekleştirilir:

- Bir tür için bir değer farklı bir tür değişkenine atandığında veya bir işleç bir işlem gerçekleştirmeden önce işleneninin veya işlenenlerinin türünü dönüştürür

- Bir tür değeri açıkça farklı bir türe yayınlandığı zaman

- Bir değer bir işleve bağımsız değişken olarak geçirildiğinde ya da bir tür bir işlevden döndürüldüğünde

Bir karakter, kısa tamsayı veya bir tamsayı bit alanı, hepsi imzalı ya da değil, tamsayı olarak bir tamsayı kullanılabileceği bir ifadede kullanılabilir. Bir `int` , özgün türün tüm değerlerini temsil ediyorsa, değer değerine dönüştürülür `int`; Aksi takdirde, öğesine `unsigned int`dönüştürülür. Bu işleme "İntegral yükseltme" adı verilir. Integral yükseltmeleri koruma değeri. Diğer bir deyişle, yükseltmeden sonraki değerin, yükseltmeden önceki ile aynı olması garanti edilir. Daha fazla bilgi için bkz. [normal aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) .

## <a name="see-also"></a>Ayrıca bkz.

[İfadeler ve atamalar](../c-language/expressions-and-assignments.md)

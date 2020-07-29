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
ms.openlocfilehash: 7d7c55c15a8f3e2a53e350da947cf524ae064a09
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231435"
---
# <a name="type-conversions-c"></a>Tür Dönüştürmeleri (C)

Tür dönüştürmeleri, belirtilen işlece ve işlenenin veya işleçlerin türüne bağlıdır. Tür dönüştürmeleri aşağıdaki durumlarda gerçekleştirilir:

- Bir tür için bir değer farklı bir tür değişkenine atandığında veya bir işleç bir işlem gerçekleştirmeden önce işleneninin veya işlenenlerinin türünü dönüştürür

- Bir tür değeri açıkça farklı bir türe yayınlandığı zaman

- Bir değer bir işleve bağımsız değişken olarak geçirildiğinde ya da bir tür bir işlevden döndürüldüğünde

Bir karakter, kısa tamsayı veya bir tamsayı bit alanı, hepsi imzalı ya da değil, tamsayı olarak bir tamsayı kullanılabileceği bir ifadede kullanılabilir. Bir **`int`** , özgün türün tüm değerlerini temsil ediyorsa, değeri öğesine dönüştürülür **`int`** ; Aksi takdirde, öğesine dönüştürülür **`unsigned int`** . Bu işleme "İntegral yükseltme" adı verilir. Integral yükseltmeleri koruma değeri. Diğer bir deyişle, yükseltmeden sonraki değerin, yükseltmeden önceki ile aynı olması garanti edilir. Daha fazla bilgi için bkz. [normal aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) .

## <a name="see-also"></a>Ayrıca bkz.

[İfadeler ve atamalar](../c-language/expressions-and-assignments.md)

---
description: 'Daha fazla bilgi edinin: tür dönüştürmeleri (C)'
title: Tür Dönüştürmeleri (C)
ms.date: 11/04/2016
helpviewer_keywords:
- conversions, type
- type conversion
- converting types
- integral promotions
- type casts, when performed
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
ms.openlocfilehash: e352a311c586631db08dc1f3e678d4242afdd797
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242866"
---
# <a name="type-conversions-c"></a>Tür Dönüştürmeleri (C)

Tür dönüştürmeleri, belirtilen işlece ve işlenenin veya işleçlerin türüne bağlıdır. Tür dönüştürmeleri aşağıdaki durumlarda gerçekleştirilir:

- Bir tür için bir değer farklı bir tür değişkenine atandığında veya bir işleç bir işlem gerçekleştirmeden önce işleneninin veya işlenenlerinin türünü dönüştürür

- Bir tür değeri açıkça farklı bir türe yayınlandığı zaman

- Bir değer bir işleve bağımsız değişken olarak geçirildiğinde ya da bir tür bir işlevden döndürüldüğünde

Bir karakter, kısa tamsayı veya bir tamsayı bit alanı, hepsi imzalı ya da değil, tamsayı olarak bir tamsayı kullanılabileceği bir ifadede kullanılabilir. Bir **`int`** , özgün türün tüm değerlerini temsil ediyorsa, değeri öğesine dönüştürülür **`int`** ; Aksi takdirde, öğesine dönüştürülür **`unsigned int`** . Bu işleme "İntegral yükseltme" adı verilir. Integral yükseltmeleri koruma değeri. Diğer bir deyişle, yükseltmeden sonraki değerin, yükseltmeden önceki ile aynı olması garanti edilir. Daha fazla bilgi için bkz. [normal aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) .

## <a name="see-also"></a>Ayrıca bkz.

[İfadeler ve atamalar](../c-language/expressions-and-assignments.md)

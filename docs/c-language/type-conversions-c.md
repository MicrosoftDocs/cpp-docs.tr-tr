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
ms.openlocfilehash: 27dcdbf810199c62b7c267270ad62ed1ed677494
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503361"
---
# <a name="type-conversions-c"></a>Tür Dönüştürmeleri (C)

Belirtilen işleç ve işleçler ve işlenen türü tür dönüştürmeleri bağlıdır. Tür dönüştürmeleri, aşağıdaki durumlarda gerçekleştirilir:

- Bir türde bir değer atandığında bir değişken farklı bir tür ya da bir işleci, işlenen veya işlenen türü bir işlem gerçekleştirmeden önce dönüştürür

- Bir türün bir değerini farklı bir türe açıkça olduğunda cast

- Bir değer bir bağımsız değişken bir işleve geçirildiğinde veya bir tür bir işlevden döndürülür

Bir karakter, kısa bir tamsayı ve tamsayı bit alanı, tüm ya da imzalı veya veya numaralandırma türünde bir nesne bir tamsayı kullanılabilir her yerde bir ifadede kullanılabilir. Varsa bir `int` değeri dönüştürdükten sonra özgün türünün tüm değerleri temsil edebilen `int`; Aksi takdirde dönüştürülür `unsigned int`. Bu işlem çağrılırken "integral yükseltme." İntegral yükseltmeler değerini korur. Diğer bir deyişle, yükseltmeden sonra bir değer olarak yükseltmeden önce aynı olması garanti edilir. Bkz: [olağan aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca Bkz.

[İfadeler ve Atamalar](../c-language/expressions-and-assignments.md)
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

Belirtilen işleç ve işleçler ve işlenen türü tür dönüştürmeleri bağlıdır. Tür dönüştürmeleri, aşağıdaki durumlarda gerçekleştirilir:

- Bir türde bir değer atandığında bir değişken farklı bir tür ya da bir işleci, işlenen veya işlenen türü bir işlem gerçekleştirmeden önce dönüştürür

- Bir türün bir değerini farklı bir türe açıkça olduğunda cast

- Bir değer bir bağımsız değişken bir işleve geçirildiğinde veya bir tür bir işlevden döndürülür

Bir karakter, kısa bir tamsayı ve tamsayı bit alanı, tüm ya da imzalı veya veya numaralandırma türünde bir nesne bir tamsayı kullanılabilir her yerde bir ifadede kullanılabilir. Varsa bir `int` değeri dönüştürdükten sonra özgün türünün tüm değerleri temsil edebilen `int`; Aksi takdirde dönüştürülür `unsigned int`. Bu işlem çağrılırken "integral yükseltme." İntegral yükseltmeler değerini korur. Diğer bir deyişle, yükseltmeden sonra bir değer olarak yükseltmeden önce aynı olması garanti edilir. Bkz: [olağan aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[İfadeler ve Atamalar](../c-language/expressions-and-assignments.md)

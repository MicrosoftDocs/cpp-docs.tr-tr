---
description: 'Daha fazla bilgi edinin: toplama (+)'
title: Toplama (+)
ms.date: 11/04/2016
helpviewer_keywords:
- pointers, adding integers
ms.assetid: b9014fee-825d-46ef-91db-5d46807081fc
ms.openlocfilehash: 33cc1284c9ab36988d9fcba2fcc9e27d052cb4cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280189"
---
# <a name="addition-"></a>Toplama (+)

Toplama işleci ( **+** ) iki işleneninin eklenmesine neden olur. Her iki işlenen de İntegral veya kayan türler olabilir ya da bir işlenen bir işaretçi ve diğeri tamsayı olabilir.

Bir işaretçiye tamsayı eklendiğinde, tamsayı değeri (*i*), işaretçinin adresleyen değerin boyutuyla çarpılarak dönüştürülür. Dönüştürmeden sonra, tamsayı değeri *i* bellek konumlarını temsil eder; burada her konum işaretçi türü tarafından belirtilen uzunluğa sahiptir. Dönüştürülen tamsayı değeri işaretçi değerine eklendiğinde sonuç, *özgün adresten gelen konumların bulunduğu* adresi temsil eden yeni bir işaretçi değeridir. Yeni işaretçi değeri, özgün işaretçi değeri ile aynı türdeki bir değere yöneliktir ve bu nedenle dizi dizinlemesi ile aynıdır (bkz. [tek boyutlu diziler](../c-language/one-dimensional-arrays.md) ve [çok boyutlu diziler](../c-language/multidimensional-arrays-c.md)). Toplam işaretçisi, üst uçta sonraki ilk konum dışında, dizinin dışına işaret ediyorsa, sonuç tanımsızdır. Daha fazla bilgi için bkz. [Işaretçi aritmetiği](../c-language/pointer-arithmetic.md).

## <a name="see-also"></a>Ayrıca bkz.

[C eklenebilir Işleçler](../c-language/c-additive-operators.md)

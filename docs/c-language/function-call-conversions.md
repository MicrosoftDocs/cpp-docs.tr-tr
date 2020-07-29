---
title: İşlev Çağrısı Dönüşümleri
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
ms.openlocfilehash: e4e84c9d4e1f25a56c0bcabcec99e5e75fcaa321
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229681"
---
# <a name="function-call-conversions"></a>İşlev Çağrısı Dönüşümleri

Bir işlev çağrısındaki bağımsız değişkenlerde gerçekleştirilen dönüştürme işleminin türü, çağrılan işlev için bildirilen bağımsız değişken türlerine sahip bir işlev prototipinin (ileri dönük bildirim) olup olmamasına bağlıdır.

Bir işlev prototipi varsa ve belirtilen bağımsız değişken türlerini içeriyorsa, derleyici tür denetimini gerçekleştirir (bkz. [işlevler](../c-language/functions-c.md)).

İşlev prototipi yoksa, işlev çağrısındaki bağımsız değişkenlerde yalnızca olağan aritmetik dönüştürmeler gerçekleştirilir. Bu dönüştürmeler, çağrıdaki her bağımsız değişkende bağımsız olarak gerçekleştirilir. Bu **`float`** , bir değerin öğesine dönüştürüldüğü anlamına gelir **`double`** ; bir veya değeri öğesine dönüştürülür **`char`** **`short`** **`int`** ve bir veya ' a **`unsigned char`** **`unsigned short`** dönüştürülür **`unsigned int`** .

## <a name="see-also"></a>Ayrıca bkz.

[Tür dönüştürmeleri](../c-language/type-conversions-c.md)

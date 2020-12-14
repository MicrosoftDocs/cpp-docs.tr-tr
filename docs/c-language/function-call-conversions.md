---
description: 'Daha fazla bilgi edinin: Function-Call dönüşümler'
title: İşlev Çağrısı Dönüşümleri
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
ms.openlocfilehash: f37cf2ef6c35cb8e7c856e1ab722a1efda2da61d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195963"
---
# <a name="function-call-conversions"></a>İşlev Çağrısı Dönüşümleri

Bir işlev çağrısındaki bağımsız değişkenlerde gerçekleştirilen dönüştürme işleminin türü, çağrılan işlev için bildirilen bağımsız değişken türlerine sahip bir işlev prototipinin (ileri dönük bildirim) olup olmamasına bağlıdır.

Bir işlev prototipi varsa ve belirtilen bağımsız değişken türlerini içeriyorsa, derleyici tür denetimini gerçekleştirir (bkz. [işlevler](../c-language/functions-c.md)).

İşlev prototipi yoksa, işlev çağrısındaki bağımsız değişkenlerde yalnızca olağan aritmetik dönüştürmeler gerçekleştirilir. Bu dönüştürmeler, çağrıdaki her bağımsız değişkende bağımsız olarak gerçekleştirilir. Bu **`float`** , bir değerin öğesine dönüştürüldüğü anlamına gelir **`double`** ; bir veya değeri öğesine dönüştürülür **`char`** **`short`** **`int`** ve bir veya ' a **`unsigned char`** **`unsigned short`** dönüştürülür **`unsigned int`** .

## <a name="see-also"></a>Ayrıca bkz.

[Tür Dönüştürmeleri](../c-language/type-conversions-c.md)

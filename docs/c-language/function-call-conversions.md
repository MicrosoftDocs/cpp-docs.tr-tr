---
title: İşlev Çağrısı Dönüşümleri
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
ms.openlocfilehash: d9f205bbbbac353b57743f8e1211b20fa3d32f05
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233231"
---
# <a name="function-call-conversions"></a>İşlev Çağrısı Dönüşümleri

Bir işlev çağrısındaki bağımsız değişkenlerde gerçekleştirilen dönüştürme işleminin türü, çağrılan işlev için bildirilen bağımsız değişken türlerine sahip bir işlev prototipinin (ileri dönük bildirim) olup olmamasına bağlıdır.

Bir işlev prototipi varsa ve bildirilen bağımsız değişken türlerini içeriyorsa, derleyici tür denetimi gerçekleştirir (bkz [işlevleri](../c-language/functions-c.md)).

İşlev prototipi yoksa, işlev çağrısındaki bağımsız değişkenlerde yalnızca olağan aritmetik dönüştürmeler gerçekleştirilir. Bu dönüştürmeler, çağrıdaki her bağımsız değişkende bağımsız olarak gerçekleştirilir. Diğer bir deyişle bir **float** değerinin bir **çift**; `char` veya **kısa** değerinin bir `int`; ve bir `unsigned char` veya **işaretsiz** dönüştürülür bir `unsigned int`.

## <a name="see-also"></a>Ayrıca bkz.

[Tür Dönüştürmeleri](../c-language/type-conversions-c.md)

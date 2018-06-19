---
title: İşlev çağrısı dönüşümleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71b0fc4468ea98f04c87c8389021f2e12d9cae69
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384502"
---
# <a name="function-call-conversions"></a>İşlev Çağrısı Dönüşümleri
Bir işlev çağrısındaki bağımsız değişkenlerde gerçekleştirilen dönüştürme işleminin türü, çağrılan işlev için bildirilen bağımsız değişken türlerine sahip bir işlev prototipinin (ileri dönük bildirim) olup olmamasına bağlıdır.  
  
 Bir işlev prototipi bulunduğundan ve bildirilen bağımsız değişken türleri içeriyorsa, derleyici tür denetlemesi gerçekleştirir (bkz [işlevleri](../c-language/functions-c.md)).  
  
 İşlev prototipi yoksa, işlev çağrısındaki bağımsız değişkenlerde yalnızca olağan aritmetik dönüştürmeler gerçekleştirilir. Bu dönüştürmeler, çağrıdaki her bağımsız değişkende bağımsız olarak gerçekleştirilir. Bunun anlamı bir **float** değeri için dönüştürülür bir **çift**; `char` veya **kısa** değeri için dönüştürülür bir `int`; ve bir `unsigned char` veya **kısa imzasız** dönüştürülür bir `unsigned int`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür Dönüştürmeleri](../c-language/type-conversions-c.md)
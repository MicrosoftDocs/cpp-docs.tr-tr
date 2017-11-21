---
title: "İşlev çağrısı dönüşümleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9f45a7b3b4aecfd25d1973e1e95ec787e958025e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="function-call-conversions"></a>İşlev Çağrısı Dönüşümleri
Bir işlev çağrısındaki bağımsız değişkenlerde gerçekleştirilen dönüştürme işleminin türü, çağrılan işlev için bildirilen bağımsız değişken türlerine sahip bir işlev prototipinin (ileri dönük bildirim) olup olmamasına bağlıdır.  
  
 Bir işlev prototipi bulunduğundan ve bildirilen bağımsız değişken türleri içeriyorsa, derleyici tür denetlemesi gerçekleştirir (bkz [işlevleri](../c-language/functions-c.md)).  
  
 İşlev prototipi yoksa, işlev çağrısındaki bağımsız değişkenlerde yalnızca olağan aritmetik dönüştürmeler gerçekleştirilir. Bu dönüştürmeler, çağrıdaki her bağımsız değişkende bağımsız olarak gerçekleştirilir. Bunun anlamı bir **float** değeri için dönüştürülür bir **çift**; `char` veya **kısa** değeri için dönüştürülür bir `int`; ve bir `unsigned char` veya **kısa imzasız** dönüştürülür bir `unsigned int`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür dönüştürmeleri](../c-language/type-conversions-c.md)
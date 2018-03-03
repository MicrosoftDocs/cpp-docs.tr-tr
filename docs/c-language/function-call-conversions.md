---
title: "İşlev çağrısı dönüşümleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2cc3d425e3f9273dfc3ad1517aa441920057d70d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="function-call-conversions"></a>İşlev Çağrısı Dönüşümleri
Bir işlev çağrısındaki bağımsız değişkenlerde gerçekleştirilen dönüştürme işleminin türü, çağrılan işlev için bildirilen bağımsız değişken türlerine sahip bir işlev prototipinin (ileri dönük bildirim) olup olmamasına bağlıdır.  
  
 Bir işlev prototipi bulunduğundan ve bildirilen bağımsız değişken türleri içeriyorsa, derleyici tür denetlemesi gerçekleştirir (bkz [işlevleri](../c-language/functions-c.md)).  
  
 İşlev prototipi yoksa, işlev çağrısındaki bağımsız değişkenlerde yalnızca olağan aritmetik dönüştürmeler gerçekleştirilir. Bu dönüştürmeler, çağrıdaki her bağımsız değişkende bağımsız olarak gerçekleştirilir. Bunun anlamı bir **float** değeri için dönüştürülür bir **çift**; `char` veya **kısa** değeri için dönüştürülür bir `int`; ve bir `unsigned char` veya **kısa imzasız** dönüştürülür bir `unsigned int`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür Dönüştürmeleri](../c-language/type-conversions-c.md)
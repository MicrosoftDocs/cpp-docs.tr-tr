---
title: Çıkarma (-) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C], subtraction
- subtraction operator, syntax
ms.assetid: 9cacba7d-20b3-4372-8a63-ba5d8ee64177
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 295c6bc33b42ed34fd476dbc72bec9dd398efa14
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386952"
---
# <a name="subtraction--"></a>Çıkarma (-)
Çıkarma işleci (**-**) ilk ikinci işlenen çıkarır. Her iki işlenen, tamsayı veya kayan türleri veya bir işlenen bir işaretçi ve diğer bir tamsayı olabilir.  
  
 İki işaretçileri çıkarılan zaman farkı imzalı tam sayı değerine türünde bir değer boyutu tarafından fark bölerek dönüştürülür, işaretçileri adresi. Tam sayı değeri türü tarafından tanımlanan **ptrdiff_t** STDDEF standart Ekle dosya. H. Sonuç türü iki adres arasındaki bellek konumlarını sayısını temsil eder. Sonuç yalnızca anlatıldığı gibi aynı dizi iki öğe için anlamlı olması garanti [işaretçi aritmetiği](../c-language/pointer-arithmetic.md).  
  
 Çıkarma işleci bir tamsayı değeri arasında bir işaretçi değeri çıkarılır, tamsayı değeri dönüştürür (*ı*) işaretçi adresleri değeri boyutuyla çarparak tarafından. Dönüştürme işleminden sonra tamsayı değeri temsil eden *ı* her konum işaretçi türü tarafından belirtilen uzunluğa sahip olduğu bellek konumlar. Dönüştürülmüş tamsayı değeri işaretçi değerinden çıkarılır, bellek adresi sonucudur *ı* özgün adresinden önce konumlar. Özgün işaretçi değeri tarafından ele türünde bir değer yeni işaretçisi işaret ediyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Ek İşleçleri](../c-language/c-additive-operators.md)
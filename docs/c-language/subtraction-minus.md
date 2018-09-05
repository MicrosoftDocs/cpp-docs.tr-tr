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
ms.openlocfilehash: 6b27eead70963665e1dd3079cf5c2b49bcfda863
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751637"
---
# <a name="subtraction--"></a>Çıkarma (-)
Çıkarma işleci (**-**) ikinci işlenen ilk çıkarır. Her iki işlenen de tamsayı veya kayan türler olabilir veya tek bir işlenen bir işaretçi ve diğer bir tamsayı olabilir.  
  
İki işaretçileri çıkartılır, fark imzalı bir tamsayı değer türünde bir değer boyutu tarafından fark bölerek dönüştürülür, işaretçiler adresi. İntegral değerinin boyutu türü tarafından tanımlanan **ptrdiff_t** STDDEF içinde standart içerme dosyası. H Sonuç, bellek konumları arasında iki adres türü sayısını temsil eder. Sonuç yalnızca içinde açıklandığı gibi aynı iki öğe için anlamlı olması garanti [işaretçi aritmetiği](../c-language/pointer-arithmetic.md).  
  
Bir işaretçi değeri bir tamsayı değeri çıkarılır, tamsayı değeri çıkarma işleci dönüştürür (*miyim*) boyutunu ele alan bir işaretçi değeri tarafından çarpmadan tarafından. Dönüştürme işleminden sonra temsil eder bir tamsayı değeri *miyim* her konum işaretçi türü tarafından belirtilen uzunluğa sahip olduğu, bellek konumları. Dönüştürülmüş tamsayı değeri çıkarılan işaretçi değer, bellek adresi sonucudur *miyim* özgün adresini önce konumları. Yeni İşaretçi, orijinal işaretçi değeri tarafından ele alınan değerini işaret eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[C Ek İşleçleri](../c-language/c-additive-operators.md)
---
title: "Maksimum dize uzunluğu | Microsoft Docs"
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
- lengths, strings
- string length, maximum
- maximum string length
- strings [C++], length
ms.assetid: 99a80e4a-6212-47b7-a6bd-bdf99bd44928
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa558129368559f3edddf9037f7f504933eb2563
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="maximum-string-length"></a>Maksimum Dize Uzunluğu
**Microsoft özel**  
  
 ANSI uyumluluğu birleştirme sonra bir dize sabit değeri içinde en çok 509 karakterleri kabul etmek için bir derleyici gerektirir. Microsoft C izin verilen uzunluk sınırını bir değişmez dize değeri, yaklaşık 2.048 bayttır. Ancak, dize sabit değeri çift tırnak işaretleri içine bölümleri oluşuyorsa önişlemci bölümleri tek bir dize halinde birleştirir ve birleştirilmiş her satır için fazladan bir bayt toplam bayt sayısı ekler.  
  
 Örneğin, bir dize 40 satırları satır (2.000 karakter) başına 50 karakterden oluşur ve 7 karakter içeren bir satır ve her satırın çift tırnak işaretleri arasına varsayalım. Bu, en fazla 2.007 bayt artı bir bayt toplam 2,008 bayt için sonlandırma null karakter ekler. Birleştirme üzerinde satırların her biri ilk 40 için fazladan bir karakteri eklenir. Bu, toplam 2.048 bayt hale getirir. Unutmayın, ancak olması durumunda satır devamlılıklar (\\) kullanılan çift tırnak işaretleri yerine her satır için fazladan bir karakter önişlemci eklemez.  
  
 Sınırlandırılmış bir kişinin 2048 bayttan daha uzun olamaz olsa da, bir dize hazır değer kabaca 65535 bayt dizeleri birleştirme tarafından oluşturulabilir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Dize Değişmez Değerleri](../c-language/c-string-literals.md)
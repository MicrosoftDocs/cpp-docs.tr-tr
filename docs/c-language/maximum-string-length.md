---
title: "Maksimum dize uzunluğu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- lengths, strings
- string length, maximum
- maximum string length
- strings [C++], length
ms.assetid: 99a80e4a-6212-47b7-a6bd-bdf99bd44928
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f3defc694e2ac3f859c160a2e34aecefd42627c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="maximum-string-length"></a>Maksimum Dize Uzunluğu
**Microsoft özel**  
  
 ANSI uyumluluğu birleştirme sonra bir dize sabit değeri içinde en çok 509 karakterleri kabul etmek için bir derleyici gerektirir. Microsoft C izin verilen uzunluk sınırını bir değişmez dize değeri, yaklaşık 2.048 bayttır. Ancak, dize sabit değeri çift tırnak işaretleri içine bölümleri oluşuyorsa önişlemci bölümleri tek bir dize halinde birleştirir ve birleştirilmiş her satır için fazladan bir bayt toplam bayt sayısı ekler.  
  
 Örneğin, bir dize 40 satırları satır (2.000 karakter) başına 50 karakterden oluşur ve 7 karakter içeren bir satır ve her satırın çift tırnak işaretleri arasına varsayalım. Bu, en fazla 2.007 bayt artı bir bayt toplam 2,008 bayt için sonlandırma null karakter ekler. Birleştirme üzerinde satırların her biri ilk 40 için fazladan bir karakteri eklenir. Bu, toplam 2.048 bayt hale getirir. Unutmayın, ancak olması durumunda satır devamlılıklar (\\) kullanılan çift tırnak işaretleri yerine her satır için fazladan bir karakter önişlemci eklemez.  
  
 Sınırlandırılmış bir kişinin 2048 bayttan daha uzun olamaz olsa da, bir dize hazır değer kabaca 65535 bayt dizeleri birleştirme tarafından oluşturulabilir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C dize değişmez değerleri](../c-language/c-string-literals.md)
---
title: "Ayıklama işleçlerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bb9e62ffd1e466fd220012717e278b79bbce3e1f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="using-extraction-operators"></a>Ayıklama İşleçlerini Kullanma
Çıkarma işleci (`>>`), hangi tüm standart C++ veri türleri için önceden programlanmış olduğu bayt Giriş akışı nesneden almak için en kolay yolu.  
  
 Biçimlendirilmiş metin giriş ayıklama işleçlerini gelen veri değerleri ayırmak için boşluğu bağlıdır. Bir metin alanı birden çok sözcükler içeriyor veya ne zaman numaralarını virgülle ayırın kullanışsız budur. Böyle bir durumda, bir alternatif biçimlendirilmemiş giriş üye fonksiyonu kullanmaktır [istream::getline](../standard-library/basic-istream-class.md#getline) dahil boşluk bir metin bloğunu okumak için ardından özel işlevler with bloğu ayrıştırılamıyor. Üye işlevi giriş akışı sınıfıyla gibi türetilen için başka bir yöntemdir `GetNextToken`, ayıklayın ve karakter verileri biçimlendirmek için IStream üyeleri çağırabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Giriş Akışları](../standard-library/input-streams.md)


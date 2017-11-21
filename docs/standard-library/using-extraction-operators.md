---
title: "Ayıklama işleçlerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ae55b0dfed94383ab4d70700a4f2b39ff8e8ea62
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-extraction-operators"></a>Ayıklama İşleçlerini Kullanma
Çıkarma işleci (`>>`), hangi tüm standart C++ veri türleri için önceden programlanmış olduğu bayt Giriş akışı nesneden almak için en kolay yolu.  
  
 Biçimlendirilmiş metin giriş ayıklama işleçlerini gelen veri değerleri ayırmak için boşluğu bağlıdır. Bir metin alanı birden çok sözcükler içeriyor veya ne zaman numaralarını virgülle ayırın kullanışsız budur. Böyle bir durumda, bir alternatif biçimlendirilmemiş giriş üye fonksiyonu kullanmaktır [istream::getline](../standard-library/basic-istream-class.md#getline) dahil boşluk bir metin bloğunu okumak için ardından özel işlevler with bloğu ayrıştırılamıyor. Üye işlevi giriş akışı sınıfıyla gibi türetilen için başka bir yöntemdir `GetNextToken`, ayıklayın ve karakter verileri biçimlendirmek için IStream üyeleri çağırabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Giriş akışları](../standard-library/input-streams.md)


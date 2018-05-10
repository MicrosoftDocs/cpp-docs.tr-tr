---
title: Ayıklama işleçlerini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96dc02c8bcd82c5b26d3cef71aa2085913ea259d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="using-extraction-operators"></a>Ayıklama İşleçlerini Kullanma

Çıkarma işleci (`>>`), hangi tüm standart C++ veri türleri için önceden programlanmış olduğu bayt Giriş akışı nesneden almak için en kolay yolu.

Biçimlendirilmiş metin giriş ayıklama işleçlerini gelen veri değerleri ayırmak için boşluğu bağlıdır. Bir metin alanı birden çok sözcükler içeriyor veya ne zaman numaralarını virgülle ayırın kullanışsız budur. Böyle bir durumda, bir alternatif biçimlendirilmemiş giriş üye fonksiyonu kullanmaktır [istream::getline](../standard-library/basic-istream-class.md#getline) dahil boşluk bir metin bloğunu okumak için ardından özel işlevler with bloğu ayrıştırılamıyor. Üye işlevi giriş akışı sınıfıyla gibi türetilen için başka bir yöntemdir `GetNextToken`, ayıklayın ve karakter verileri biçimlendirmek için IStream üyeleri çağırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)<br/>

---
title: Ayıklama İşleçlerini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
ms.openlocfilehash: 1fc6ffd2f033dfe3df60260f734d93b79d6824f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626232"
---
# <a name="using-extraction-operators"></a>Ayıklama İşleçlerini Kullanma

Çıkarma işleci (`>>`), tüm standart C++ veri türleri için programlanmış, bir giriş akışı nesneden bayt almak için en kolay yoludur.

Biçimlendirilmiş metin giriş ayıklama işleçlerini gelen veri değerlerinin ayırmak için beyaz boşluğu bağlıdır. Bu, bir metin alanı birden çok sözcük içerdiğinde veya numaralarını virgülle ayırın, kullanışsız olur. Böyle bir durumda bir alternatif biçimlendirilmemiş giriş üye işlevini kullanmaktır [istream::getline](../standard-library/basic-istream-class.md#getline) metin bloğu dahil boşlukla okumak için daha sonra blok özel işlevler ile ayrıştırılamıyor. Bir giriş akışı sınıfı olan üye bir işlev gibi türetmek için başka bir yöntemdir `GetNextToken`, ayıklayın ve karakter verileri biçimlendirmek için istream üyelerini çağırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)<br/>

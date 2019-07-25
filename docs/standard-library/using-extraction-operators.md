---
title: Ayıklama İşleçlerini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
ms.openlocfilehash: 7950984973f8df236905128ce4b5336ecb874b7f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458034"
---
# <a name="using-extraction-operators"></a>Ayıklama İşleçlerini Kullanma

Tüm standart C++ veri türleri`>>`için önceden programlanan ayıklama işleci (), bir giriş akışı nesnesinden bayt almanın en kolay yoludur.

Biçimlendirilen metin girişi ayıklama işleçleri, gelen veri değerlerini ayırmak için boşluğa bağımlıdır. Bir metin alanı birden çok sözcük içerdiğinde veya virgüller ayrı olduğunda bu kullanışlıdır. Böyle bir durumda, bir alternatif, boş alan içeren bir metin bloğunu okumak için [IStream:: getline](../standard-library/basic-istream-class.md#getline) biçimlendirilmemiş giriş üye işlevini kullanmak ve ardından bloğu özel işlevlerle ayrıştırmaktır. Başka bir yöntem de gibi bir üye işlev `GetNextToken`içeren bir giriş akışı sınıfı türetmektir. Bu, karakter verilerini ayıklamak ve biçimlendirmek için IStream üyelerini çağırabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)

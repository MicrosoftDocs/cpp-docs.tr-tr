---
description: 'Hakkında daha fazla bilgi edinin: ayıklama Işleçlerini kullanma'
title: Ayıklama İşleçlerini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
ms.openlocfilehash: 11115ed9d7f83b5e4d8cefe088c638afe8d95f38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153583"
---
# <a name="using-extraction-operators"></a>Ayıklama İşleçlerini Kullanma

`>>`Tüm standart C++ veri türleri için önceden programlanan ayıklama işleci (), bir giriş akışı nesnesinden bayt almanın en kolay yoludur.

Biçimlendirilen metin girişi ayıklama işleçleri, gelen veri değerlerini ayırmak için boşluğa bağımlıdır. Bir metin alanı birden çok sözcük içerdiğinde veya virgüller ayrı olduğunda bu kullanışlıdır. Böyle bir durumda, bir alternatif, boş alan içeren bir metin bloğunu okumak için [IStream:: getline](../standard-library/basic-istream-class.md#getline) biçimlendirilmemiş giriş üye işlevini kullanmak ve ardından bloğu özel işlevlerle ayrıştırmaktır. Başka bir yöntem de gibi bir üye işlev içeren bir giriş akışı sınıfı türetmektir `GetNextToken` . Bu, karakter verilerini ayıklamak ve biçimlendirmek için IStream üyelerini çağırabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş akışları](../standard-library/input-streams.md)

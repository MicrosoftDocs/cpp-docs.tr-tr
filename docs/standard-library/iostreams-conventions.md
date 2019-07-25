---
title: iostreams Kuralları
ms.date: 11/04/2016
helpviewer_keywords:
- iostream header
- C++ Standard Library, iostreams
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
ms.openlocfilehash: 222a65f60b231ba4b3768131c15d6e0d736f211e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449010"
---
# <a name="iostreams-conventions"></a>iostreams Kuralları

İostreams üstbilgileri, metin ile kodlanmış formlar ve dış dosyalara giriş ve çıkış arasındaki dönüştürmeleri destekler:

|||
|-|-|
|[\<fstream >](../standard-library/fstream.md)|[\<iomanıp >](../standard-library/iomanip.md)|
|[\<iOS >](../standard-library/ios.md)|[\<iosfwd >](../standard-library/iosfwd.md)|
|[\<iostream >](../standard-library/iostream.md)|[\<IStream >](../standard-library/istream.md)|
|[\<ostream >](../standard-library/ostream.md)|[\<sstream >](../standard-library/sstream.md)|
|[\<streamarabelleğe >](../standard-library/streambuf.md)|[\<strstream >](../standard-library/strstream.md)|

İostreams en basit kullanımı yalnızca, [ \<ıostream >](../standard-library/iostream.md)üstbilgisini dahil etmeniz gerekir. Daha sonra, standart girişi okumak için [cin](../standard-library/iostream.md#cin) veya [wcin](../standard-library/iostream.md#wcin) değerlerini ayıklayabilirsiniz. Bunu yapmak için kurallar, Class [Basic_istream sınıfının](../standard-library/basic-istream-class.md)açıklamasında özetlenmiştir. Ayrıca, Standart çıktıyı yazmak için [cout](../standard-library/iostream.md#cout) veya [wcout](../standard-library/iostream.md#wcout) 'a değer ekleyebilirsiniz. Bunu yapmak için kurallar, Class [basic_ostream sınıfının](../standard-library/basic-ostream-class.md)açıklamasında özetlenmiştir. Hem ayıklayıcıları hem de ınsertors için ortak biçim denetimi, Class [basic_ios Sınıfı](../standard-library/basic-ios-class.md)tarafından yönetilir. Nesne ayıklama ve ekleme işlemi için bu biçim bilgilerini düzenleme, birkaç işleme yer alır.

Ad ile açtığınız dosyalarda, [ \<fstream >](../standard-library/fstream.md)olarak belirtilen sınıfları kullanarak aynı Iostreams işlemlerini gerçekleştirebilirsiniz. Sınıfından [basic_string sınıfının](../standard-library/basic-string-class.md)Iostreams ve nesneleri arasında dönüştürme yapmak için [ \<sstream >](../standard-library/sstream.md)içinde belirtilen sınıfları kullanın. C dizeleriyle aynı yapmak için, [ \<strstream >](../standard-library/strstream.md)içinde belirtilen sınıfları kullanın.

Kalan üstbilgiler, genellikle Iostreams sınıflarının yalnızca en gelişmiş kullanıcılarına doğrudan ilgi sağlayan destek hizmetleri sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[C++Standart kitaplığa genel bakış](../standard-library/cpp-standard-library-overview.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

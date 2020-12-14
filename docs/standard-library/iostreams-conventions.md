---
description: 'Daha fazla bilgi edinin: Iostreams kuralları'
title: iostreams Kuralları
ms.date: 11/04/2016
helpviewer_keywords:
- iostream header
- C++ Standard Library, iostreams
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
ms.openlocfilehash: 3676c6aa14a5ebac1d39ed50821449caa7313e40
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231400"
---
# <a name="iostreams-conventions"></a>iostreams Kuralları

İostreams üstbilgileri, metin ile kodlanmış formlar ve dış dosyalara giriş ve çıkış arasındaki dönüştürmeleri destekler:

[\<fstream>](../standard-library/fstream.md)\
[\<iomanip>](../standard-library/iomanip.md)\
[\<ios>](../standard-library/ios.md)\
[\<iosfwd>](../standard-library/iosfwd.md)\
[\<iostream>](../standard-library/iostream.md)\
[\<istream>](../standard-library/istream.md)\
[\<ostream>](../standard-library/ostream.md)\
[\<sstream>](../standard-library/sstream.md)\
[\<streambuf>](../standard-library/streambuf.md)\
[\<strstream>](../standard-library/strstream.md)

İostreams en basit kullanımı yalnızca üstbilgiyi dahil etmeniz gerekir [\<iostream>](../standard-library/iostream.md) . Daha sonra, standart girişi okumak için [cin](../standard-library/iostream.md#cin) veya [wcin](../standard-library/iostream.md#wcin) değerlerini ayıklayabilirsiniz. Bunu yapmak için kurallar, sınıf [Basic_istream sınıfının](../standard-library/basic-istream-class.md)açıklamasında özetlenmiştir. Ayrıca, Standart çıktıyı yazmak için [cout](../standard-library/iostream.md#cout) veya [wcout](../standard-library/iostream.md#wcout) 'a değer ekleyebilirsiniz. Bunu yapmak için kurallar, sınıf [basic_ostream sınıfının](../standard-library/basic-ostream-class.md)açıklamasında özetlenmiştir. Hem ayıklayıcıları hem de ınsertors için ortak biçim denetimi, sınıf [basic_ios Sınıfı](../standard-library/basic-ios-class.md)tarafından yönetilir. Nesne ayıklama ve ekleme işlemi için bu biçim bilgilerini düzenleme, birkaç işleme yer alır.

' De belirtilen sınıfları kullanarak, adıyla açtığınız dosyalarda aynı Iostreams işlemlerini gerçekleştirebilirsiniz [\<fstream>](../standard-library/fstream.md) . Sınıf [basic_string](../standard-library/basic-string-class.md)sınıfının Iostreams ve nesneleri arasında dönüştürme yapmak için, içinde belirtilen sınıfları kullanın [\<sstream>](../standard-library/sstream.md) . C dizeleriyle aynı yapmak için, içinde belirtilen sınıfları kullanın [\<strstream>](../standard-library/strstream.md) .

Kalan üstbilgiler, genellikle Iostreams sınıflarının yalnızca en gelişmiş kullanıcılarına doğrudan ilgi sağlayan destek hizmetleri sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

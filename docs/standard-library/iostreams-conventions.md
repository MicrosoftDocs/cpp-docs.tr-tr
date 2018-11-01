---
title: iostreams Kuralları
ms.date: 11/04/2016
helpviewer_keywords:
- iostream header
- C++ Standard Library, iostreams
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
ms.openlocfilehash: 52cdd06385994e49ff793e40318ca4cbbbcfcda0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50645568"
---
# <a name="iostreams-conventions"></a>iostreams Kuralları

İostreams üstbilgileri harici dosyalara metin ve kodlanmış formları, giriş ve çıkış arasındaki dönüştürmeleri destekler:

|||
|-|-|
|[\<fstream >](../standard-library/fstream.md)|[\<iomanip >](../standard-library/iomanip.md)|
|[\<iOS >](../standard-library/ios.md)|[\<iosfwd >](../standard-library/iosfwd.md)|
|[\<iostream >](../standard-library/iostream.md)|[\<istream >](../standard-library/istream.md)|
|[\<ostream >](../standard-library/ostream.md)|[\<sstream >](../standard-library/sstream.md)|
|[\<streambuf >](../standard-library/streambuf.md)|[\<strstream >](../standard-library/strstream.md)|

En basit iostreams yalnızca başlığı dahil gerektirir [ \<iostream >](../standard-library/iostream.md). Ardından değerleri ayıklayabilir [cin](../standard-library/iostream.md#cin) veya [wcin](../standard-library/iostream.md#wcin) standart giriş okumak için. Bunu yapmak için kuralları bu nedenle sınıf açıklamasında ana hatlarıyla özetlenen [basic_istream sınıfı](../standard-library/basic-istream-class.md). Değerleri için de ekleyebilirsiniz [cout](../standard-library/iostream.md#cout) veya [wcout](../standard-library/iostream.md#wcout) standart çıkışını yazmak için. Bunu yapmak için kuralları bu nedenle sınıf açıklamasında ana hatlarıyla özetlenen [basic_ostream sınıfı](../standard-library/basic-ostream-class.md). Biçim Denetimi ayıklayıcıları hem insertors ortak sınıf tarafından yönetilen [basic_ios sınıfı](../standard-library/basic-ios-class.md). Bu biçim bilgilerini de gerçekleştirebilirler ayıklanması ve nesne ekleme düzenleme birkaç manipülatörleri, İl olur.

Aynı ada göre açık dosyaları iostreams işlemleri gerçekleştirebilir, sınıfları kullanılarak bildirilen [ \<fstream >](../standard-library/fstream.md). İostreams sınıfındaki nesneler arasında dönüştürmek için [basic_string sınıfı](../standard-library/basic-string-class.md), bildirilen sınıfları kullanan [ \<sstream >](../standard-library/sstream.md). C dizeleri ile aynı yapmak için bildirilen sınıfları kullanın [ \<strstream >](../standard-library/strstream.md).

Kalan üstbilgileri genellikle ilgi doğrudan iostreams sınıfları yalnızca en gelişmiş kullanıcılar için destek hizmetleri sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

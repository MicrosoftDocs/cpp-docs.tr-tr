---
title: iostreams kuralları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- iostream header
- C++ Standard Library, iostreams
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8d5d6408f51bc3a0bf0fc0ca997635c5b371dcf6
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="iostreams-conventions"></a>iostreams Kuralları

İostreams üstbilgileri dış dosyalara metin kodlanmış form ve giriş ve çıkış arasında dönüştürme destekler:

|||
|-|-|
|[\<fstream >](../standard-library/fstream.md)|[\<iomanip >](../standard-library/iomanip.md)|
|[\<iOS >](../standard-library/ios.md)|[\<iosfwd >](../standard-library/iosfwd.md)|
|[\<iostream >](../standard-library/iostream.md)|[\<istream >](../standard-library/istream.md)|
|[\<ostream >](../standard-library/ostream.md)|[\<sstream >](../standard-library/sstream.md)|
|[\<streambuf >](../standard-library/streambuf.md)|[\<strstream >](../standard-library/strstream.md)|

En basit iostreams yalnızca başlığı dahil kullanımını [ \<iostream >](../standard-library/iostream.md). Ardından değerlerinden ayıklayabilirsiniz [cin](../standard-library/iostream.md#cin) veya [wcin](../standard-library/iostream.md#wcin) standart giriş okunamıyor. Bunu yapmak için kurallar nedenle sınıf açıklamasında özetlenen [basic_istream sınıfı](../standard-library/basic-istream-class.md). Değerleri de ekleyebilirsiniz [cout](../standard-library/iostream.md#cout) veya [wcout](../standard-library/iostream.md#wcout) standart çıkışını yazmak için. Bunu yapmak için kurallar nedenle sınıf açıklamasında özetlenen [basic_ostream sınıfı](../standard-library/basic-ostream-class.md). Biçim Denetimi ayıklayıcıları ve insertors için ortak sınıfı tarafından yönetilen [basic_ios sınıfı](../standard-library/basic-ios-class.md). Ayıklanması ve nesneleri ekleme bu biçimi bilgileri gerçekleştirebilirler düzenleme birkaç manipülatörleri il olur.

Gerçekleştirebileceğiniz adıyla açık dosyalarda aynı iostreams işlemleri, sınıfları kullanma bildirilen [ \<fstream >](../standard-library/fstream.md). İostreams ve sınıfın nesneleri arasında dönüştürme için [basic_string sınıfı](../standard-library/basic-string-class.md), bildirilen sınıfları kullanan [ \<sstream >](../standard-library/sstream.md). C dizeleri ile aynı yapmak için bildirilen sınıfları kullanması [ \<strstream >](../standard-library/strstream.md).

Kalan üstbilgileri genellikle ilgi doğrudan iostreams sınıfların yalnızca en gelişmiş kullanıcılar için destek hizmetleri sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

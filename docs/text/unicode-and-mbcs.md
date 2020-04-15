---
title: Unicode ve MBCS
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], Unicode
- MFC [C++], character sets
- character sets [C++], multibyte
- run-time libraries [C++], language portability
- character sets [C++], Unicode
- Unicode [C++], MFC and C run-time functions
- multibyte characters [C++]
- runtime [C++], language portability
ms.assetid: 677baec6-71b4-4579-94df-64f18bc117c4
ms.openlocfilehash: 063c8b39ee0d29403b382b57a236f2a3e8759e3f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375750"
---
# <a name="unicode-and-mbcs"></a>Unicode ve MBCS

Microsoft Hazırlık Sınıfları (MFC) kitaplığı, Visual C++için C çalışma zamanı kitaplığı ve Visual C++ geliştirme ortamı, uluslararası programlamanıza yardımcı olmak için etkinleştirilir. Şunları sağlar:

- Windows'da Unicode standardı için destek. Unicode geçerli standarttır ve mümkün olduğunca kullanılmalıdır.

   Unicode, tüm diller için yeterli kodlama sağlayan 16 bit karakter kodlamasidır. Tüm ASCII karakterleri genişletildikçe Unicode'a dahil edilir.

- Tüm platformlarda çift bayt karakter kümesi (DBCS) olarak adlandırılan çok bayt karakter kümesi (MBCS) biçimi için destek.

   DBCS karakterleri 1 veya 2 bayttan oluşur. Bazı bayt aralıkları kurşun bayt olarak kullanılmak üzere bir kenara bırakılır. Bir kurşun bayt, onun ve aşağıdaki iz baytın tek bir 2 bayt genişliğinde bir karakter oluşturduğunu belirtir. Baytların hangi baytlar olduğunu takip etmelisiniz. Belirli bir çok bayt karakter kümesinde, kurşun baytlar belirli bir aralık içinde, iz baytları gibi düşer. Bu aralıklar çakıştığında, verilen bir baytın kurşun bayt mı yoksa iz bayt ı olarak mı çalıştığını belirlemek için bağlamı değerlendirmek gerekebilir.

- Uluslararası pazarlar için yazılmış uygulamaların MBCS programlaması basitleştirmek araçlar için destek.

   Windows işletim sisteminin MBCS özellikli bir sürümünde çalıştırıldığında, tümleşik kaynak kod düzenleyicisi, hata ayıklayıcı ve komut satırı araçları da dahil olmak üzere Visual C++ geliştirme sistemi tamamen MBCS özelliklidir. Daha fazla bilgi için [Visual C++ 'da MBCS Desteği'ne](../text/mbcs-support-in-visual-cpp.md)bakın.

> [!NOTE]
> Bu belgede, MBCS çok bayt karakterler için Unicode olmayan tüm desteği tanımlamak için kullanılır. Visual C++'da MBCS her zaman DBCS anlamına gelir. 2 bayttan daha geniş karakter kümeleri desteklenmez.

Tanım olarak, ASCII karakter kümesi tüm multibayt karakter kümelerinin bir alt kümesidir. Birçok çok bayt karakter kümesinde, 0x00 - 0x7F aralığındaki her karakter, ASCII karakter kümesinde aynı değere sahip karakterle aynıdır. Örneğin, hem ASCII hem de MBCS karakter dizelerinde, 1 bayt NULL karakterinin ('\0') değeri 0x00'dir ve sonlandırıcı null karakterini gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Metin ve Dizeleri](../text/text-and-strings-in-visual-cpp.md)<br/>
[Uluslararası Etkinleştirme](../text/international-enabling.md)

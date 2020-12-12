---
description: Bkz. Unicode ve MBCS hakkında daha fazla bilgi
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
ms.openlocfilehash: 4fc5afc447612a3f08067185072cd4f116ab80c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114981"
---
# <a name="unicode-and-mbcs"></a>Unicode ve MBCS

Microsoft Foundation Sınıfları (MFC) kitaplığı, Visual C++ için C çalışma zamanı kitaplığı ve Visual C++ geliştirme ortamı, uluslararası programlama konusunda yardımcı olmak için etkinleştirilmiştir. Şunları sağlar:

- Windows üzerinde Unicode standardı desteği. Unicode geçerli standarttır ve mümkün olan her durumda kullanılmalıdır.

   Unicode, tüm diller için yeterli kodlama sağlayan 16 bitlik bir karakter kodlamasında bulunur. Tüm ASCII karakterleri, iletildiklerinde karakter olarak Unicode 'a dahildir.

- Tüm platformlarda çift baytlı karakter kümesi (DBCS) olarak adlandırılan çok baytlı karakter kümesi (MBCS) için destek.

   DBCS karakterleri 1 veya 2 bayttan oluşur. Bazı bayt aralıkları, ön bayt olarak kullanılmak üzere ayarlanır. Bir ön bayt, bunun ve aşağıdaki iz baytının tek bir 2 baytlık karakteri bulunduğunu belirtir. Hangi baytların ön bayt olduğunu takip etmeniz gerekir. Belirli bir çok baytlı karakter kümesinde, ön baytlar belirli bir Aralık içinde yer aldığı için, bu baytları izleyin. Bu aralıklar çakıştığında, belirli bir baytın bir ön bayt veya bir iz baytı olarak çalışıp çalışmadığını anlamak üzere bağlamını değerlendirmek gerekli olabilir.

- Uluslararası pazarlar için yazılmış uygulamaların MBCS programlamasını basitleştiren araçlar için destek.

   Windows işletim sisteminin MBCS özellikli bir sürümünde çalıştırıldığında, Tümleşik kaynak kodu Düzenleyicisi, hata ayıklayıcı ve komut satırı araçları da dahil olmak üzere Visual C++ geliştirme sistemi tamamen MBCS etkindir. Daha fazla bilgi için bkz. [Visual C++ 'Da mbcs desteği](../text/mbcs-support-in-visual-cpp.md).

> [!NOTE]
> Bu belgede, çok baytlı karakterler için Unicode olmayan tüm desteği betimleyen MBCS kullanılır. Visual C++, MBCS her zaman DBCS anlamına gelir. 2 bayttan daha geniş karakter kümeleri desteklenmez.

Tanım olarak, ASCII karakter kümesi tüm çok baytlı karakter kümelerinin bir alt kümesidir. Çok baytlı karakter kümelerinde, 0x00-0x7F aralığındaki her bir karakter, ASCII karakter kümesinde aynı değere sahip olan karakterle aynıdır. Örneğin, hem ASCII hem de MBCS karakter dizeleri içinde, 1 baytlık NULL karakter (' \ 0 ') 0x00 değerine sahiptir ve Sonlandırıcı null karakteri gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Metin ve dizeler](../text/text-and-strings-in-visual-cpp.md)<br/>
[Uluslararası etkinleştirme](../text/international-enabling.md)

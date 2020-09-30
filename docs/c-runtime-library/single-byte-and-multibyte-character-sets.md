---
title: Tek Baytlı ve Çok Baytlı Karakter Kümeleri
description: Microsoft çalışma zamanı kitaplığındaki tek ve çok baytlı karakter kümelerine giriş.
ms.topic: conceptual
ms.date: 11/04/2016
helpviewer_keywords:
- SBCS (single byte character set)
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- character sets [C++], single byte
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
ms.openlocfilehash: 6668285915ab9f1939c1baf8a2d3da2d00543528
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590179"
---
# <a name="single-byte-and-multibyte-character-sets"></a>Tek Baytlı ve Çok Baytlı Karakter Kümeleri

ASCII karakter kümesi, 0x00-0x7F aralığındaki karakterleri tanımlar. 0x00-0x7F aralığındaki karakterleri ASCII karakter kümesiyle aynı şekilde tanımlayan ve ayrıca 0x80-0xFF ' den genişletilmiş bir karakter kümesi tanımlayan, genellikle Avrupa, diğer birçok karakter kümesi vardır.  8 bit, tek baytlı karakter kümesi (SBCS), ASCII karakter kümesini ve birçok Avrupa dili için karakter kümelerini temsil etmek için yeterlidir. Ancak, Japonca Kanji gibi bazı Avrupa olmayan karakter kümelerinde, tek baytlık kodlama düzeninde temsil edilemeyecek kadar çok daha fazla karakter bulunur ve bu nedenle çok baytlı karakter kümesi (MBCS) kodlaması gerekir.

> [!NOTE]
> Microsoft çalışma zamanı kitaplığı 'ndaki birçok SBCS yordamı, uygun şekilde çok baytlı bayt, karakter ve dizeleri işler. Çok baytlı karakter kümeleri, ASCII karakter kümesini bir alt küme olarak tanımlar. Çok baytlı karakter kümelerinde, 0x00-0x7F aralığındaki her bir karakter, ASCII karakter kümesinde aynı değere sahip olan karakterle aynıdır. Örneğin, hem ASCII hem de MBCS karakter dizeleri içinde, tek baytlık null karakter (' \ 0 ') 0x00 değerine sahiptir ve Sonlandırıcı null karakteri gösterir.

Çok baytlı bir karakter kümesi, hem tek baytlı hem de iki baytlık karakterlerden oluşabilir. Çok baytlı karakter dizesi, tek baytlı ve çift baytlık karakterlerin bir karışımını içerebilir. İki baytlık çok baytlı bir karakterin bir ön bayt ve iz baytı vardır. Belirli bir çok baytlı karakter kümesinde, ön baytlar belirli bir Aralık içinde yer aldığı için, bu baytları izleyin. Bu aralıklar çakıştığında, belirli bir baytın bir ön bayt veya bir iz baytı olarak çalışıp çalışmadığını anlamak için bağlamı değerlendirmeniz gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>

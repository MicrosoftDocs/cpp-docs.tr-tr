---
title: Tek Baytlı ve Çok Baytlı Karakter Kümeleri
ms.date: 11/04/2016
helpviewer_keywords:
- SBCS (single byte character set)
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- character sets [C++], single byte
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
ms.openlocfilehash: a6a0f3aaaa463297b7c51b035acc7b2f4a40b6cf
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444656"
---
# <a name="single-byte-and-multibyte-character-sets"></a>Tek Baytlı ve Çok Baytlı Karakter Kümeleri

ASCII karakter kümesi, 0x00-0x7F aralığındaki karakterleri tanımlar. 0x00-0x7F aralığındaki karakterleri ASCII karakter kümesiyle aynı şekilde tanımlayan ve ayrıca 0x80-0xFF ' den genişletilmiş bir karakter kümesi tanımlayan, genellikle Avrupa, diğer birçok karakter kümesi vardır. Bu nedenle, bir 8 bit, tek baytlık karakter kümesi (SBCS), ASCII karakter kümesini ve birçok Avrupa dili için karakter kümelerini temsil etmek için yeterlidir. Ancak, Japonca Kanji gibi bazı Avrupa olmayan karakter kümelerinde, tek baytlık kodlama düzeninde temsil edilemeyecek kadar çok daha fazla karakter bulunur ve bu nedenle çok baytlı karakter kümesi (MBCS) kodlaması gerekir.

> [!NOTE]
> Microsoft çalışma zamanı kitaplığı 'ndaki birçok SBCS yordamı, uygun şekilde çok baytlı bayt, karakter ve dizeleri işler. Çok baytlı karakter kümeleri, ASCII karakter kümesini bir alt küme olarak tanımlar. Çok baytlı karakter kümelerinde, 0x00-0x7F aralığındaki her bir karakter, ASCII karakter kümesinde aynı değere sahip olan karakterle aynıdır. Örneğin, hem ASCII hem de MBCS karakter dizeleri içinde, tek baytlık null karakter (' \ 0 ') 0x00 değerine sahiptir ve Sonlandırıcı null karakteri gösterir.

Çok baytlı bir karakter kümesi, tek baytlık ve iki baytlık karakterlerden oluşabilir. Bu nedenle çok baytlı karakter dizesi, tek baytlı ve çift baytlık karakterlerin bir karışımını içerebilir. İki baytlık çok baytlı bir karakterin bir ön bayt ve iz baytı vardır. Belirli bir çok baytlı karakter kümesinde, ön baytlar belirli bir Aralık içinde yer aldığı için, bu baytları izleyin. Bu aralıklar çakıştığında, belirli bir baytın bir ön bayt veya bir iz baytı olarak çalışıp çalışmadığını anlamak için bu içeriğin değerlendirilmesi gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>

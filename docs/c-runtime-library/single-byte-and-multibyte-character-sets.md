---
title: Tek Baytlı ve Çok Baytlı Karakter Kümeleri
ms.date: 11/04/2016
f1_keywords:
- c.character.multibyte
helpviewer_keywords:
- SBCS (single byte character set)
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- character sets [C++], single byte
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
ms.openlocfilehash: 1870fed732e5b940edb7690f9c3b58bb39c24572
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50645392"
---
# <a name="single-byte-and-multibyte-character-sets"></a>Tek Baytlı ve Çok Baytlı Karakter Kümeleri

ASCII karakter kümesi 0x00 - 0x7F aralıktaki karakterleri tanımlar. Bir 0x00 aralığındaki karakterleri tanımlayan diğer karakter kümesi sayısı, öncelikle Avrupa vardır - 0x7F ASCII karakter için aynı şekilde ayarlayın ve ayrıca bir Genişletilmiş karakter kümesinde 0x80 - 0xFF tanımlayın. Bu nedenle 8-bit, tek baytlı karakter kümesi (SBCS) ASCII karakter kümesi ve bunun yanı sıra birçok Avrupa dilleri için karakter kümesini temsil etmek yeterli olur. Ancak, bazı Avrupa dışı karakter kümeleri, Japonca Kanji gibi bir tek bayt kodlama düzeni temsil edilebilir ve çok baytlı karakter kodlaması (MBCS) ayarlayın. Bu nedenle gerekli olandan çok daha fazla karakter içerir.

> [!NOTE]
> Microsoft Çalışma Zamanı Kitaplığı'ndaki birçok SBCS yordamlarını, çok baytlı bayt, karakterleri ve dizeleri uygun şekilde işleyin. Birçok çok baytlı karakter kümeleri, ASCII karakter bir alt kümesini tanımlar. Çok baytlı karakter kümelerinin her karakter aralığı 0x00 - 0x7F aynı değere sahip ASCII karakter kümesinden karakter aynıdır. Örneğin, ASCII ve MBCS karakter dizeleri bir bayt null karakteri ('\0') 0x00 değerine sahiptir ve sondaki boş karakter gösterir.

Çok baytlı karakter kümesi tek baytlık hem iki baytlık karakter olabilir. Bu nedenle bir çok baytlı karakter dizesi tek baytlı ve çift baytlık karakterler bir karışımını içerebilir. Bir iki baytlık çok baytlı karakterin ön baytı ve sondaki baytı sahiptir. Baytlar gibi belirli bir çok baytlı karakter kümesi içinde belirli bir aralıkta ön baytlar ayrılır. Bu aralıklar üst üste, belirli bir bayt bir ön bayt veya bir bayt olarak çalışıp çalışmadığını belirlemek için belirli bir içerik değerlendirmek gerekli olabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>

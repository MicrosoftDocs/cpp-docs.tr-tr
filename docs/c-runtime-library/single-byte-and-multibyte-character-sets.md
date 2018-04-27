---
title: Tek baytlı ve çok baytlı karakter kümesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- c.character.multibyte
dev_langs:
- C++
helpviewer_keywords:
- SBCS (single byte character set)
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- character sets [C++], single byte
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d6c339f1ab2eecfac5f037e711f19d5ee9323fc
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="single-byte-and-multibyte-character-sets"></a>Tek Baytlı ve Çok Baytlı Karakter Kümeleri

ASCII karakter kümesi 0x00 - 0x7F aralıktaki karakterleri tanımlar. Bir 0x00 aralıktaki karakterleri tanımlayan diğer karakter kümesi sayısı, öncelikle Avrupa vardır - ASCII karakter için aynı 0x7F ayarlayın ve aynı zamanda bir Genişletilmiş karakter kümesinden 0x80 - 0xFF tanımlar. Bu nedenle bir 8 bit, tek bayt karakter kümesi (SBCS) ASCII karakter kümesi gibi birçok Avrupa dilleri için karakter kümesi temsil etmek yeterli olur. Ancak, Japonca Kanji gibi bazı Avrupa dışı karakter kümesi de tek baytlık bir kodlama düzeni temsil edilebilir ve bu nedenle çok baytlı karakter kümesi (MBCS) kodlaması gerektiren daha çok daha fazla karakter içerir.

> [!NOTE]
> Microsoft Çalışma Zamanı Kitaplığı'nda birçok SBCS yordamları birden çok baytlı bayt, karakterler ve dizeleri uygun olarak işler. Çok baytlı karakter kümeleri ASCII karakter bir alt kümesini tanımlar. Çok baytlı karakter kümelerinin her karakter aralığı 0x00 - 0x7F aynı değere sahip ASCII karakter kümesinden karakter aynıdır. Örneğin, ASCII ve MBCS karakter dizeleri bir bayt NULL karakteri ('\0') 0x00 değerine sahiptir ve sonlandırıcı boş karakteri gösterir.

Birden çok baytlı karakter kümesi tek baytlı ve iki baytlık karakterler içerebilir. Bu nedenle çok baytlı karakter dizesi tek baytlı ve çift baytlık karakterler bir karışımını içerebilir. İki baytlık birden çok baytlı karakter baytı ve sondaki bayt vardır. Baytlar gibi belirli bir çok baytlı karakter kümesinde belirli bir aralığa ön baytlar ayrılır. Bu aralıklar üst üste, verilen baytın baytı veya sondaki bayt olarak çalışıp çalışmadığını belirlemek için belirli bağlamı değerlendirmek gerekli olabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategorilere göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>

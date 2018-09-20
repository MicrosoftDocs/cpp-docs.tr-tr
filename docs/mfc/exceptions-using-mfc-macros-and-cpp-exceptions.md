---
title: 'Özel durumlar: MFC makroları ve C++ özel durumlarını kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exception objects [MFC]
- memory leaks [MFC], exception object not deleted
- exception handling [MFC], MFC
- try-catch exception handling [MFC], mixing MFC macros and C++ keywords
- exception objects [MFC], deleting
- exceptions [MFC], MFC macros vs. C++ keywords
- catch blocks [MFC], mixed
- exception handling [MFC], mixed-language
- nested try blocks [MFC]
- catch blocks [MFC], explicitly deleting code in
- try-catch exception handling [MFC], nested try blocks
- heap corruption [MFC]
- nested catch blocks [MFC]
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c12a281962e807c8d1bd28284accb0ddcd62456
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434407"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>Özel Durumlar: MFC Makroları ve C++ Özel Durumlarını Kullanma

Bu makalede, hem MFC özel durum işleme makroları ve C++ özel durum işleme anahtar sözcükleri kullanan kodu yazmada dikkat edilmesi gerekenler açıklanmaktadır.

Bu makalede, aşağıdaki konular ele alınmaktadır:

- [Özel durum anahtar sözcüklerini ve makroları karıştırma](#_core_mixing_exception_keywords_and_macros)

- [Try blokları içindeki catch blokları](#_core_try_blocks_inside_catch_blocks)

##  <a name="_core_mixing_exception_keywords_and_macros"></a> Özel durum anahtar sözcüklerini ve makroları karıştırma

MFC özel durum makroları ve C++ özel durum anahtar sözcüklerini aynı programda karıştırabilirsiniz. Ancak, bunlar için kapsam dışına çıkmasına olduğunda özel durum işleme anahtar sözcüklerini kullanarak kod desteklemez makroları özel durum nesneleri otomatik olarak silmek için C++ özel durum anahtar sözcüklerini aynı blokta ile MFC makroları karıştırılamaz. Daha fazla bilgi için bkz [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).

Makroları ve anahtar sözcükler arasındaki temel fark, özel durum kapsam dışına çıktığında makroları "Otomatik" yakalanan bir özel durumu Sil ' dir. Anahtar sözcükleri kullanarak kod desteklemez; bir catch bloğu içinde Yakalanan özel durumların açıkça silinmelidir. Makrolar ve C++ özel durum anahtar sözcüklerini karıştırma bir özel durum nesnesi silinmedi bellek sızıntılarının neden veya bir özel durum iki kez silindiğinde Bozulması yığın.

Aşağıdaki kod, örneğin, özel durum işaretçisi geçersiz kılar:

[!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

Sorun nedeniyle oluşur `e` "İç" dışında yürütme başarılı olduğunda silinir **CATCH** blok. Kullanarak **THROW_LAST** yerine makrosu **THROW** deyimi neden olacak "dış" **CATCH** geçerli bir işaretçi almaya engelle:

[!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

##  <a name="_core_try_blocks_inside_catch_blocks"></a> Try blokları içindeki Catch blokları

Geçerli özel durumu içinden yeniden atılamıyor bir **deneyin** içinde blok bir **CATCH** blok. Aşağıdaki örnek, geçersiz:

[!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

Daha fazla bilgi için [özel durumlar: özel durum içeriklerini İnceleme](../mfc/exceptions-examining-exception-contents.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)


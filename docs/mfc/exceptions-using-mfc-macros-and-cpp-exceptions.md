---
title: 'Özel durumlar: MFC makroları ve C++ özel durumlarını kullanma'
ms.date: 11/04/2016
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
ms.openlocfilehash: 00e88ddabf3a8e8b591bebae7ebc8ced0e1dc637
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406021"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>Özel durumlar: MFC makroları ve C++ özel durumlarını kullanma

Bu makalede, hem MFC özel durum işleme makroları ve C++ özel durum işleme anahtar sözcükleri kullanan kodu yazmada dikkat edilmesi gerekenler açıklanmaktadır.

Bu makalede, aşağıdaki konular ele alınmaktadır:

- [Özel durum anahtar sözcüklerini ve makroları karıştırma](#_core_mixing_exception_keywords_and_macros)

- [Try blokları içindeki catch blokları](#_core_try_blocks_inside_catch_blocks)

##  <a name="_core_mixing_exception_keywords_and_macros"></a> Özel durum anahtar sözcüklerini ve makroları karıştırma

MFC özel durum makroları ve C++ özel durum anahtar sözcüklerini aynı programda karıştırabilirsiniz. Ancak, bunlar için kapsam dışına çıkmasına olduğunda özel durum işleme anahtar sözcüklerini kullanarak kod desteklemez makroları özel durum nesneleri otomatik olarak silmek için C++ özel durum anahtar sözcüklerini aynı blokta ile MFC makroları karıştırılamaz. Daha fazla bilgi için bkz [özel durumlar: Yakalama ve özel durumları silme](../mfc/exceptions-catching-and-deleting-exceptions.md).

Makroları ve anahtar sözcükler arasındaki temel fark, özel durum kapsam dışına çıktığında makroları "Otomatik" yakalanan bir özel durumu Sil ' dir. Anahtar sözcükleri kullanarak kod desteklemez; bir catch bloğu içinde Yakalanan özel durumların açıkça silinmelidir. Makrolar ve C++ özel durum anahtar sözcüklerini karıştırma bir özel durum nesnesi silinmedi bellek sızıntılarının neden veya bir özel durum iki kez silindiğinde Bozulması yığın.

Aşağıdaki kod, örneğin, özel durum işaretçisi geçersiz kılar:

[!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

Sorun nedeniyle oluşur `e` "İç" dışında yürütme başarılı olduğunda silinir **CATCH** blok. Kullanarak **THROW_LAST** yerine makrosu **THROW** deyimi neden olacak "dış" **CATCH** geçerli bir işaretçi almaya engelle:

[!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

##  <a name="_core_try_blocks_inside_catch_blocks"></a> Try blokları içindeki Catch blokları

Geçerli özel durumu içinden yeniden atılamıyor bir **deneyin** içinde blok bir **CATCH** blok. Aşağıdaki örnek, geçersiz:

[!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

Daha fazla bilgi için [özel durumlar: Özel durum içeriklerini İnceleme](../mfc/exceptions-examining-exception-contents.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
